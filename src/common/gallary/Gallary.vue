<template>
  <div class="container" @click="handleGallaryClick">
    <div class="wrapper">
      <swiper :options="swiperOptions">
        <swiper-slide>
          <img class="swiper-img" src="http://img1.qunarzz.com/sight/p0/1706/b3/b3bbc6bb89a2c944a3.img.jpg_r_800x800_4d1c0ea8.jpg" />
        </swiper-slide>
        <swiper-slide>
          <img class="swiper-img" src="http://img1.qunarzz.com/sight/p0/1706/2a/2a00027a55b61b34a3.img.jpg_r_800x800_e67b25b4.jpg" />
        </swiper-slide>
        <swiper-slide>
          <img class="swiper-img" src="http://img1.qunarzz.com/sight/p0/1706/ad/ad5810fb51f7ed2aa3.img.jpg_r_800x800_e465d53e.jpg" />
        </swiper-slide>
      </swiper>
      <div class="swiper-pagination" slot="pagination"></div>
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
    bottom: .6rem;
    font-size: .24rem;
  }
</style>
