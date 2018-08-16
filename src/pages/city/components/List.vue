<template>
  <div class="list" ref="wrapper">
    <div>
      <div class="area">
        <div class="title border-top border-bottom">您的位置</div>
        <div class="button-list">
          <div class="button-wrapper">
            <div class="button border-bottom">{{this.$store.state.city}}</div>
          </div>
        </div>
      </div>
      <div class="area">
        <div class="title border-top border-bottom">热门城市</div>
        <div class="button-list">
          <div class="button-wrapper" @click="handleCityClick(item.name)" v-for="item of hot" :key="item.id">
            <div class="button border-bottom">{{item.name}}</div>
          </div>
        </div>
      </div>
      <div class="area" v-for="(item, key) of city" :key="key" :ref="key">
        <div class="title border-top border-bottom">{{key}}</div>
        <div class="item-list" @click="handleCityClick(itemlist.name)" v-for="itemlist of item" :key="itemlist.id">
          <div class="item border-bottom">{{itemlist.name}}</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import BScroll from 'better-scroll'

export default {
  name: 'CityList',
  props: {
    hot: Array,
    city: Object,
    letter: String
  },
  methods: {
    handleCityClick (city) {
      this.$store.commit('changeCity', city)
      this.$router.push('/')
    }
  },
  mounted () {
    this.scroll = new BScroll(this.$refs.wrapper)
  },
  watch: {
    letter () {
      if (this.letter) {
        const element = this.$refs[this.letter][0]
        this.scroll.scrollToElement(element)
      }
    }
  }
}
</script>

<style scoped>
  .list {
    font-size: .28rem;
    overflow: hidden;
    position: absolute;
    top: 1.58rem;
    left: 0;
    right: 0;
    bottom: 0;
  }
  .area .title {
    line-height: .4rem;
    background: #eee;
    padding: .15rem;
  }
  .area .button-list {
    padding: .1rem .6rem .1rem .1rem;
    overflow: hidden;
  }
  .area .button-list .button-wrapper {
    width: 33.33%;
    float: left;
  }
  .area .button-list .button-wrapper .button {
    text-align: center;
    margin: .1rem;
    padding: .1rem 0;
    border: .02rem solid #ccc;
    border-radius: .1rem;
  }
  .area .item-list .item {
    line-height: .64rem;
    padding: .1rem;
    padding-left: .2rem;
  }
</style>
