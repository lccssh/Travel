<template>
  <div>
    <div class="banner" @click="handleBannerClick">
      <div class="banner-img-wrapper">
        <img class="banner-img-content" :src="bannerImg" />
        <div class="banner-info">
          <div class="banner-title">{{sightName}}</div>
          <div class="banner-number"><span class="iconfont img-icon">&#xe655;</span>{{gallaryImgs.length}}</div>
        </div>
      </div>
    </div>
    <common-gallary v-show="showGallary" @close="handleGallaryClose" :gallaryImgs="gallaryImgs"></common-gallary>
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
  props: {
    sightName: String,
    bannerImg: String,
    gallaryImgs: Array
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
</style>
