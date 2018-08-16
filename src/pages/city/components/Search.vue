<template>
  <div class="search-wrapper">
    <div class="search">
      <input v-model="keyword" type="text" class="search-input" placeholder="输入城市名或拼音">
    </div>
    <div class="search-content" v-show="keyword" ref="search">
      <ul>
        <li v-for="(item, index) of list" :key="index" class="search-item border-bottom">{{item.name}}</li>
      </ul>
    </div>
  </div>
</template>

<script>
import BScroll from 'better-scroll'

export default {
  name: 'CitySearch',
  data () {
    return {
      keyword: '',
      list: [],
      timer: null
    }
  },
  props: {
    city: Object
  },
  watch: {
    keyword () {
      if (this.timer) {
        clearTimeout(this.timer)
      }
      if (!this.keyword) {
        this.result = []
      }
      this.timer = setTimeout(() => {
        const result = []
        for (let i in this.city) {
          this.city[i].forEach((value) => {
            if (value.spell.indexOf(this.keyword) > -1 || value.name.indexOf(this.keyword) > -1) {
              result.push(value)
            }
          })
        }
        this.list = result
      }, 100)
    }
  },
  mounted () {
    this.scroll = new BScroll(this.$refs.search)
  }
}
</script>

<style scoped>
  .search {
    height: .72rem;
    padding: 0 .1rem;
    background: #00bcde;
    font-size: .28rem;
  }
  .search .search-input {
    width: 100%;
    height: .62rem;
    line-height: .62rem;
    text-align: center;
    border-radius: .06rem;
    color: #666;
  }
  .search-content {
    overflow: hidden;
    position: absolute;
    top: 1.58rem;
    left: 0;
    right: 0;
    bottom: 0;
    background: #fff;
    z-index: 20;
  }
  .search-content .search-item {
    line-height: .64rem;
    padding-left: .2rem;
    font-size: .28rem;
  }
</style>
