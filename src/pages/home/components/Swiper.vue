<template>
  <div class="wrapper">
    <swiper :options="swiperOption">
      <swiper-slide v-for="item of swiperList" :key="item.id">
        <img class="swiper-img" :src="item.imgUrl">
      </swiper-slide>
      <div class="swiper-pagination"  slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeSwiper',
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true
      },
      swiperList: [{
        id: '1001',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1807/40/1d7be74ed1584002.jpg_750x200_c41233c9.jpg'
      }, {
        id: '1002',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1807/c6/44fce1467be17702.jpg_750x200_406f5fc3.jpg'
      }]
    }
  }
}
</script>

<style lang="scss">
  .wrapper{
    height: 0;
    width: 100%;
    overflow: hidden;
    padding-bottom: 26%;
    background :#EEE;
    .swiper-pagination-bullet-active{
      background: #FFF;
    }
    .swiper-img{
      width: 100%;
    }
  }
</style>
