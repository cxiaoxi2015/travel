<template>
  <div class="icons">
    <swiper :options="swiperOption">
      <swiper-slide v-for="(page,index) of pages" :key="index">
        <div class="icon" v-for="item of page" :key="item.id">
          <div class="icon-img">
            <img :src="item.imgUrl">
          </div>
          <p class="icon-desc">{{ item.desc }}</p>
        </div>
      </swiper-slide>
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeIcons',
  data () {
    return {
      swiperOption: {
        autoplay: false
      }
    }
  },
  props: {
    list: Array
  },
  computed: {
    pages () {
      const pages = []
      this.list.forEach((item,index) => {
        // 向下取正
        const page = Math.floor(index / 8)
        if(!pages[page]) {
          pages[page] = []
        }
        pages[page].push(item)
      })
      return pages
    }
  }
}
</script>

<style lang="scss" scoped>
  @import '~style/varibles.scss';
  @import '~style/mixins.scss';
  .icons{
    /*height: 0;*/
    /*padding-bottom: 50%;*/
    /*overflow: hidden;*/
    margin-top: .1rem;
    .swiper-container{
      height: 0;
      padding-bottom: 50%;
    }
    .icon{
      overflow: hidden;
      float: left;
      width: 25%;
      padding-bottom: 25%;
      position: relative;
      height: 0;
      .icon-img{
        position: absolute;
        top: 0;
        left: 0;
        right: 0;
        bottom: .44rem;
        box-sizing: border-box;
        padding: .1rem;
        & > img{
          height: 100%;
          display: block;
          margin: 0 auto;
        }
      }
      .icon-desc{
        position: absolute;
        left: 0;
        right: 0;
        bottom: 0;
        height: .44rem;
        line-height: .44rem;
        text-align: center;
        color: $darkTextColor;
        @include ellipsis;
      }
    }
  }
</style>
