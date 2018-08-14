<template>
  <div class="list" ref="wrapper">
    <div>
      <div class="area">
        <div class="title border-top border-bottom">您的位置</div>
        <div class="button-list">
          <div class="button-wrapper">
            <div class="button border-bottom">北京</div>
          </div>
          <div class="button-wrapper">
            <div class="button border-bottom">北京</div>
          </div>
          <div class="button-wrapper">
            <div class="button border-bottom">北京</div>
          </div>
          <div class="button-wrapper">
            <div class="button border-bottom">北京</div>
          </div>
        </div>
      </div>
      <div class="area">
        <div class="title border-top border-bottom">热门城市</div>
        <div class="button-list">
          <div class="button-wrapper">
            <div class="button border-bottom">北京</div>
          </div>
          <div class="button-wrapper">
            <div class="button border-bottom">北京</div>
          </div>
          <div class="button-wrapper">
            <div class="button border-bottom">北京</div>
          </div>
          <div class="button-wrapper">
            <div class="button border-bottom">北京</div>
          </div>
        </div>
      </div>
      <div class="area">
        <div class="title border-top border-bottom">A</div>
        <div class="item-list">
          <div class="item border-bottom">阿拉尔</div>
          <div class="item border-bottom">阿拉尔</div>
          <div class="item border-bottom">阿拉尔</div>
          <div class="item border-bottom">阿拉尔</div>
          <div class="item border-bottom">阿拉尔</div>
          <div class="item border-bottom">阿拉尔</div>
        </div>
      </div>
      <div class="area">
        <div class="title border-top border-bottom">A</div>
        <div class="item-list">
          <div class="item border-bottom">阿拉尔</div>
          <div class="item border-bottom">阿拉尔</div>
          <div class="item border-bottom">阿拉尔</div>
          <div class="item border-bottom">阿拉尔</div>
          <div class="item border-bottom">阿拉尔</div>
          <div class="item border-bottom">阿拉尔</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import BScroll from 'better-scroll'

export default {
  name: 'CityList',
  mounted () {
    this.scroll = new BScroll(this.$refs.wrapper)
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
