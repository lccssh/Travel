<template>
  <div class="wrapper">
    <div class="title">热销推荐</div>
    <ul>
      <router-link tag="li" :to="'/detail/' + item.id" class="item border-bottom" v-for="item of list" :key="item.id">
        <div class="item-img-wrapper">
          <img class="item-img" :src="item.imgUrl" />
        </div>
        <div class="item-content">
          <div class="item-title">{{item.title}}</div>
          <div class="item-rating">
            <Rate v-model="value" />
            <span class="rating">4295条评论</span>
          </div>
          <div class="item-desc">
            <span class="price">￥150</span><span class="down">起</span>
            <span class="area">鸠江区</span>
          </div>
        </div>
      </router-link>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeRecommend',
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
    margin-top: .1rem;
    line-height: .8rem;
    background: #eee;
    text-indent: .2rem;
  }
  .item {
    display: flex;
    height: 1.9rem;
  }
  .item .item-img {
    width: 1.7rem;
    height: 1.7rem;
    padding: .1rem;
    margin: .1rem;
  }
  .item .item-content {
    flex: 1;
    margin-top: .26rem;
    margin-left: .1rem;
  }
  .item .item-content .item-title {
    height: .44rem;
    font-size: .32rem;
    line-height: .44rem;
  }
  .item .item-content .item-rating {
    padding-top: .1rem;
  }
  .item .item-content .item-rating .ivu-rate {
    font-size: .26rem;
    line-height: .32rem;
  }
  .item .item-content .item-desc {
    padding-top: .1rem;
    line-height: .44rem;
  }
  .item .item-content .item-desc .price {
    font-size: .32rem;
    color: #ff8300;
    float: left;
  }
  .item .item-content .item-desc .down {
    display: inline-block;
    padding-top: .05rem;
  }
  .item .item-content .item-desc .area {
    float: right;
    padding-top: .05rem;
    padding-right: .2rem;
  }
</style>
