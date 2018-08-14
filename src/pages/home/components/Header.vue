<template>
  <div class="header">
    <div class="header-left">
      <span class="iconfont back-icon">&#xe624;</span>
    </div>
    <div class="header-input">
      <span class="iconfont search-icon">&#xe632;</span>
      输入城市/景点/游玩主题
    </div>
    <router-link to="/city">
      <div class="header-right">
        北京<span class="iconfont down-icon">&#xe628;</span>
      </div>
    </router-link>
  </div>
</template>

<script>
export default {
  name: 'HomeHeader',
  props: {
    city: String
  }
}
</script>

<style scoped>
  .header {
    display: flex;
    line-height: .86rem;
    background: #00bcd4;
    color: #fff;
  }
  .header .header-left {
    width: .64rem;
    float: left;
  }
  .header .header-left .back-icon {
    text-align: center;
    display: block;
    padding-left: .1rem;
    font-size: .4rem;
  }
  .header .header-input {
    flex: 1;
    background: #fff;
    margin-top: .12rem;
    height: .64rem;
    border-radius: .1rem;
    margin-left: .2rem;
    margin-right: .2rem;
    color: #ccc;
    font-size: .26rem;
    line-height: .64rem;
  }
  .header .header-input .search-icon {
    padding-left: .1rem;
  }
  .header .header-right {
    width: 1.04rem;
    float: right;
    font-size: .28rem;
    color: #fff;
  }
  .header .header-right .down-icon {
    font-size: .24rem;
  }
</style>
