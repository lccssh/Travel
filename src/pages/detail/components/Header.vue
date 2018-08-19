<template>
  <div>
    <div class="header-abs" v-show="showAbs">
      <div class="back-bg">
        <router-link to="/">
          <span class="iconfont abs-back-icon">&#xe624;</span>
        </router-link>
      </div>
    </div>
    <div class="header-fixed" v-show="!showAbs" :style="opacityStyle">
      <router-link to="/">
        <span class="iconfont fixed-back-icon">&#xe624;</span>
      </router-link>
      景点详情
    </div>
  </div>
</template>

<script>
export default {
  name: 'DetailHeader',
  data () {
    return {
      showAbs: true,
      opacityStyle: {
        opacity: 0
      }
    }
  },
  methods: {
    handleScroll () {
      const top = document.documentElement.scrollTop
      if (top > 60) {
        let opacity = top / 140
        // 限制 opacity 最大值为一且必须为一
        opacity = opacity > 1 ? 1 : opacity
        this.opacityStyle = { opacity }
        this.showAbs = false
      } else {
        this.showAbs = true
      }
    }
  },
  activated () {
    window.addEventListener('scroll', this.handleScroll)
  },
  deactivated () {
    window.removeEventListener('scroll', this.handleScroll)
  }
}
</script>

<style scoped>
  .header-abs {
    position: absolute;
    left: .1rem;
    top: .1rem;
  }
  .header-abs .back-bg {
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
  .header-abs .back-bg .abs-back-icon {
    color: #fff;
  }
  .header-fixed {
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    height: .86rem;
    line-height: .86rem;
    text-align: center;
    color: #fff;
    background: #00bcd4;
    font-size: .32rem;
    z-index: 2;
  }
  .header-fixed .fixed-back-icon {
    position: absolute;
    left: .15rem;
    font-size: .4rem;
    color: #fff;
  }
</style>
