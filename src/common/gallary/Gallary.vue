<template>
  <div class="container" @click="handleGallaryClick">
    <div class="wrapper">
      <swiper :options="swiperOptions">
        <swiper-slide v-for="(item, index) of gallaryImgs" :key="index">
          <img class="swiper-img" :src="item" />
        </swiper-slide>
      <div class="swiper-pagination" slot="pagination"></div>
      </swiper>
    </div>
  </div>
</template>

<script>
export default {
  name: 'CommonGallary',
  data () {
    return {
      swiperOptions: {
        pagination: '.swiper-pagination',
        paginationType: 'fraction',
        observeParents: true,
        observer: true
      }
    }
  },
  props: {
    gallaryImgs: Array
  },
  methods: {
    handleGallaryClick () {
      this.$emit('close')
    }
  }
}
</script>

<style scoped>
  .container {
    display: flex;
    flex-direction: column;
    justify-content: center;
    z-index: 99;
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background: #000;
  }
  .container .wrapper {
    height: 0;
    width: 100%;
    padding-bottom: 66.625%;
  }
  .container .wrapper .swiper-img {
    width: 100%;
  }
  .container .wrapper .swiper-pagination {
    color: #fff;
    font-size: .24rem;
  }
</style>
