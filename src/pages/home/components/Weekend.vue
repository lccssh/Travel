<template>
  <div class="wrapper">
    <div class="title">周末去哪儿</div>
    <ul>
      <li class="item border-bottom" v-for="item of itemList" :key="item.id">
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
  data () {
    return {
      value: 5,
      itemList: [{
        id: '0001',
        imgUrl: 'http://img1.qunarzz.com/sight/source/1606/56/56a7a471ea2986.jpg_r_640x214_68aed5b3.jpg',
        title: '芜湖必游TOP5',
        desc: '云开看树色，江静听潮声'
      }, {
        id: '0002',
        imgUrl: 'http://img1.qunarzz.com/sight/source/1509/c6/26884ae7d9969c.jpg_r_640x214_c3e02a8c.jpg',
        title: '当地人带你玩',
        desc: '接天莲叶无穷碧，映日荷花别样红'
      }, {
        id: '0003',
        imgUrl: 'http://img1.qunarzz.com/sight/source/1511/fd/0285e145e82233.jpg_r_640x214_b5f10121.jpg',
        title: '黔县旅游',
        desc: '走进黄山，探寻桃花源里的人家'
      }, {
        id: '0004',
        imgUrl: 'http://img1.qunarzz.com/sight/source/1505/16/bd5c6a9c972052.jpg_r_640x214_1bfe355c.jpg',
        title: '酷爽漂流一夏',
        desc: '烈日炎炎，我们一起打水战吧'
      }, {
        id: '0005',
        imgUrl: 'http://img1.qunarzz.com/sight/source/1505/7e/a5ec29839a2a9e.jpg_r_640x214_53b4f72d.jpg',
        title: '黄山必游TOP10',
        desc: '清泉，轻舟'
      }]
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
    padding-bottom: 33.9%;
  }
  .item .item-img {
    width: 100%;
  }
  .item .item-content {
    text-indent: .1rem;
    margin: .15rem;
  }
  .item .item-content .item-title {
    height: .3rem;
    font-size: .3rem;
    line-height: .3rem;
  }
  .item .item-content .item-desc {
    padding-top: .1rem;
    line-height: .44rem;
  }
</style>
