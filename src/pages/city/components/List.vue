<template>
  <div class="list" ref="wrapper">
    <div>
      <div class="area">
        <div class="title border-topbottom">当前城市</div>
        <div class="button-list">
          <div class="button-wrapper">
            <div class="button">北京</div>
          </div>
        </div>
      </div>
      <div class="area">
        <div class="title border-topbottom">热门城市</div>
        <div class="button-list">
          <div class="button-wrapper" v-for="item of hot" :key="item.id">
            <div class="button">{{ item.name }}</div>
          </div>
        </div>
      </div>
      <div class="area" v-for="(item,key) of cities" :key="key">
        <div class="title border-topbottom">{{ key }}</div>
        <div class="item-list" v-for="innerItem of item" :key="innerItem.id">
          <div class="item border-bottom">{{ innerItem.name }}</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Bscroll from 'better-scroll'
export default {
  name: 'CityList',
  mounted () {
    this.scroll = new Bscroll(this.$refs.wrapper)
  },
  props: {
    hot: Array,
    cities: Object
  }
}
</script>

<style lang="scss" scoped>
  @import '~style/varibles.scss';
  .border-topbottom{
    &:before{
      border-color: #CCC;
    }
    &:after{
      border-color: #CCC;
    }
  }
  .border-bottom{
    &:before{
      border-color: #CCC;
    }
  }
  .list{
    position: absolute;
    top: 1.58rem;
    left: 0;
    right: 0;
    bottom: 0;
    overflow: hidden;
    .title{
      line-height: .54rem;
      background: #EEE;
      padding-left: .2rem;
      color: #666;
    }
    .button-list{
      padding: .1rem;
      overflow: hidden;
      padding: .1rem .6rem .1rem .1rem;
      .button-wrapper{
        width: 33.33%;
        float: left;
        .button{
          margin: .1rem;
          text-align: center;
          border: .02rem solid #CCC;
          padding: .1rem 0;
          border-radius: .06rem;
        }
      }
    }
    .item-list{
      .item{
        line-height: .76rem;
        padding-left: .2rem;
      }
    }
  }
</style>
