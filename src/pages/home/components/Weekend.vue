<!-- 周末去哪 -->
<template>
  <div>
    <div class="title">周末去哪</div>
    <ul>
      <li class="item border-bottom" v-for="item of recommendList" :key="item.id">
        <div class="item-img-wrapper">
          <img class="item-img" :src="item.imgUrl">
        </div>
        <div class="item-info">
          <p class="item-title">{{ item.title }}</p>
          <p class="item-desc">{{ item.desc }}</p>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
  export default {
    name: 'HomeWeekend',
    data () {
      return {
        recommendList: [{
          id: '0001',
          imgUrl: 'http://img1.qunarzz.com/sight/source/1505/b7/8a08a1023062b3.jpg_r_640x214_d7cb475c.jpg',
          title: '大连圣亚海洋世界',
          desc: '浪漫大连首站，浪漫的海洋主题公园'
        }, {
          id: '0002',
          imgUrl: 'http://img1.qunarzz.com/sight/source/1505/b7/8a08a1023062b3.jpg_r_640x214_d7cb475c.jpg',
          title: '大连圣亚海洋世界',
          desc: '浪漫大连首站，浪漫的海洋主题公园'
        }, {
          id: '0003',
          imgUrl: 'http://img1.qunarzz.com/sight/source/1505/b7/8a08a1023062b3.jpg_r_640x214_d7cb475c.jpg',
          title: '大连圣亚海洋世界',
          desc: '浪漫大连首站，浪漫的海洋主题公园'
        }]
      }
    }
  }
</script>

<style lang="scss" scoped>
  @import '~style/mixins';
  .title{
    line-height: .8rem;
    background: #EEE;
    text-indent: .2rem;
    margin-top: .4rem;
  }
  .item{
    .item-img{
      width: 100%;
    }
    .item-info{
      padding: .1rem;
      .item-title{
        line-height: .54rem;
        font-size: .32rem;
        @include ellipsis;
      }
      .item-desc{
        line-height: .4rem;
        color: #CCC;
      }
    }
    .item-img-wrapper{
      overflow: hidden;
      height: 0;
      padding-bottom: 37%;
    }
  }
</style>
