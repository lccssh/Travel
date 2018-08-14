<template>
  <div class="wrapper">
    <swiper :options="swiperOption" v-if="showSwiper">
      <swiper-slide v-for="item of list" :key="item.id">
        <img class="swiper-img" :src="item.imgUrl" />
      </swiper-slide>
      <div class="swiper-pagination"  slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeSwiper',
  props: {
    list: Array
  },
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true // 轮播图循环播放
      }
    }
  },
  computed: {
    showSwiper () {
      return this.list.length
    }
  }
}
</script>

<style scoped>
  .wrapper >>> .swiper-pagination-bullet-active {
    background: #fff;
  }
  .wrapper {
    width: 100%;
    height: 0;
    overflow: hidden;
    padding-bottom: 26.67%;
    background: #eee;
  }
  .swiper-img {
    width: 100%
  }
</style>
