<template>
  <div class="header">
    城市选择
    <router-link to="/">
      <div class="iconfont header-back">&#xe624;</div>
    </router-link>
  </div>
</template>

<script>
export default {
  name: 'CityHeader'
}
</script>

<style lang="scss" scoped>
  @import '~style/varibles.scss';
  .header{
    height: $headerHeight;
    line-height: $headerHeight;
    overflow: hidden;
    text-align: center;
    color: #FFF;
    background: $bgColor;
    font-size: .32rem;
    position: relative;
    .header-back{
      text-align: center;
      font-size: .4rem;
      width: .64rem;
      position: absolute;
      top: 0;
      left: 0;
      color: #FFF;
    }
  }
</style>
