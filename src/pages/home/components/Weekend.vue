<template>
  <div class="wrapper">
    <div class="title">周末去哪儿</div>
    <ul>
      <li class="item" v-for="item of list" :key="item.id">
        <div class="item-img-wrapper">
          <img class="item-img" :src="item.imgUrl" />
        </div>
        <div class="item-content">
          <div class="item-title">{{item.title}}</div>
          <div class="item-desc">{{item.desc}}</div>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeRecommand',
  props: {
    list: Array
  },
  data () {
    return {
      value: 5
    }
  }
}
</script>

<style scoped>
  .title {
    font-size: .28rem;
    line-height: .8rem;
    background: #eee;
    text-indent: .2rem;
  }
  .item-img-wrapper {
    overflow: hidden;
    height: 0;
    padding-bottom: 37.09%;
  }
  .item .item-img {
    width: 100%;
  }
  .item .item-content {
    text-indent: .1rem;
    padding: .1rem;
    margin-top: .12rem;
  }
  .item .item-content .item-title {
    height: .3rem;
    font-size: .3rem;
    line-height: .3rem;
  }
  .item .item-content .item-desc {
    line-height: .44rem;
  }
</style>
