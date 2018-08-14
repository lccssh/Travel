<template>
  <div class="header">
    城市选择
    <router-link to="/">
      <span class="iconfont back-icon">&#xe624;</span>
    </router-link>
  </div>
</template>

<script>
export default {
  name: 'CityHeader'
}
</script>

<style scoped>
  .header {
    position: relative;
    overflow: hidden;
    height: .86rem;
    line-height: .86rem;
    text-align: center;
    color: #fff;
    background: #00bcd4;
    font-size: .32rem;
  }
  .header .back-icon {
    position: absolute;
    left: .15rem;
    font-size: .32rem;
    color: #fff;
  }
</style>
