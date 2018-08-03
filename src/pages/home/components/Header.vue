<template>
  <div class="header">
    <div class="header-left"><div class="iconfont back-icon">&#xe624;</div></div>
    <div class="header-input"><span class="iconfont">&#xe632;</span>输入城市/景点/游玩主题</div>
    <router-link to="city">
      <div class="header-right">{{ city }} <span class="iconfont city-icon">&#xe64a;</span></div>
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

<style lang="scss" scoped>
  @import '~style/varibles.scss';
  .header{
    line-height: $headerHeight;
    display: flex;
    background: $bgColor;
    color: #FFF;
    .header-left{
      float: left;
      width: .64rem;
      .back-icon{
        text-align: center;
        font-size: .4rem;
      }
    }
    .header-input{
      flex: 1;
      margin-top: .12rem;
      margin-left: .2rem;
      height: .64rem;
      line-height: .64rem;
      background: #FFF;
      border-radius: .1rem;
      color: #CCC;
      padding-left: .2rem;
    }
    .header-right{
      float: right;
      width: 1.24rem;
      text-align: center;
      color: #FFF;
      .city-icon{
        margin-left: -0.04rem;
        font-size: .24rem;
      }
    }
  }
</style>
