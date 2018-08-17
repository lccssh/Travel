<template>
  <div>
    <div class="banner" @click="handleBannerClick">
      <div class="banner-img-wrapper">
        <img class="banner-img-content" src="//img1.qunarzz.com/sight/p0/1607/a5/a50187e22a0c3fac0.water.jpg_600x330_141d6098.jpg" />
        <div class="banner-info">
          <div class="banner-title">合肥万达文化旅游城</div>
          <div class="banner-number"><span class="iconfont img-icon">&#xe655;</span>3</div>
        </div>
        <div class="banner-back">
          <div class="back-bg">
            <router-link to="/">
              <span class="iconfont back-icon">&#xe624;</span>
            </router-link>
          </div>
        </div>
      </div>
    </div>
    <common-gallary v-show="showGallary" @close="handleGallaryClose"></common-gallary>
  </div>
</template>

<script>
import CommonGallary from 'common/gallary/Gallary'

export default {
  name: 'DetailBanner',
  data () {
    return {
      showGallary: false
    }
  },
  methods: {
    handleBannerClick () {
      this.showGallary = true
    },
    handleGallaryClose () {
      this.showGallary = false
    }
  },
  components: {
    CommonGallary
  }
}
</script>

<style scoped>
  .banner .banner-img-wrapper {
    position: relative;
    overflow: hidden;
    height: 0;
    padding-bottom: 55%;
  }
  .banner-img-wrapper .banner-img-content {
    width: 100%;
  }
  .banner .banner-info {
    position: absolute;
    left: 0;
    right: 0;
    bottom: 0;
    padding: 0 .2rem;
    padding-bottom: .36rem;
    min-width: .4rem;
    background-image: linear-gradient(top, rgba(0,0,0,0), rgba(0,0,0,0.80));
  }
  .banner .banner-info .banner-title {
    position: relative;
    font-size: .36rem;
    line-height: .4rem;
    color: #fff;
    text-shadow: 0 1px 2px rgba(0,0,0,0.7);
  }
  .banner .banner-info .banner-number {
    position: absolute;
    bottom: .84rem;
    width: 1.2rem;
    height: .4rem;
    font-size: .24rem;
    color: #fff;
    background: rgba(0,0,0,.5);
    border-radius: .24rem;
    line-height: .4rem;
    text-align: center;
  }
  .banner .banner-info .banner-number .img-icon {
    display: inline-block;
    font-size: .2rem;
    padding-right: .12rem;
  }
  .banner .banner-back {
    position: absolute;
    left: .1rem;
    top: .1rem;
  }
  .banner .banner-back .back-bg {
    background: rgba(0,0,0,.5);
    width: .72rem;
    height: .72rem;
    border-radius: 50%;
    color: #fff;
    font-size: .44rem;
    font-weight: bolder;
    text-align: center;
    vertical-align: middle;
  }
  .banner .banner-back .back-bg .back-icon {
    color: #fff;
  }
</style>
