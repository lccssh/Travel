<template>
  <div class="city">
   <ul class="list">
     <li class="item">A</li>
     <li class="item">A</li>
     <li class="item">A</li>
     <li class="item">A</li>
     <li class="item">A</li>
   </ul>
  </div>
</template>

<script>
export default {
  name: 'CityAplhabet'
}
</script>

<style scoped>
  .list {
    display: flex;
    flex-direction: column;
    justify-content: center;
    position: absolute;
    top: 1.58rem;
    right: 0;
    bottom: 0;
    width: .4rem;
  }
  .list .item {
    text-align: center;
    font-size: .32rem;
    color: #00bcd4;
    line-height: .4rem;
  }
</style>
