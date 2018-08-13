<template>
  <div class="wrapper">
    <div class="title">热销推荐</div>
    <ul>
      <li class="item border-bottom" v-for="item of itemList" :key="item.id">
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
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeRecommand',
  data () {
    return {
      value: 5,
      itemList: [{
        id: '0001',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1605/b4/b48e483ebd5feea690.img.jpg_200x200_86f5f2a6.jpg',
        title: '芜湖方特水上乐园（三期）'
      }, {
        id: '0002',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1705/eb/eb128df3c858ab92a3.img.jpg_200x200_d6f6c506.jpg',
        title: '芜湖方特梦幻王国（一期）'
      }, {
        id: '0003',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/201405/23/90f4adb0fece26edf42722a54c3fedc4.jpg_200x200_16b17651.jpg',
        title: '芜湖方特欢乐世界（二期）'
      }, {
        id: '0004',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1711/8e/8e54393ae24c8c46a3.img.jpg_200x200_33c49b5d.jpg',
        title: '芜湖大浦乡村世界'
      }, {
        id: '0005',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1608/67/670cdeaaadd7beffa3.water.jpg_200x200_b6f74aeb.jpg',
        title: '鸠兹古镇'
      }, {
        id: '0006',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1803/dd/dd62beca4b43db6ca3.img.jpg_200x200_04e8b1b5.jpg',
        title: '新华联大白鲸海洋公园'
      }]
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
