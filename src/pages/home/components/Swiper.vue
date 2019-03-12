<template>
  <div class="wrapper">
    <swiper :options="swiperOption" v-if="swiperList.length">
        <swiper-slide v-for="item of swiperList" :key="item.id">
          <div>
            <img class="swiper-image" :src="item.imgUrl">
          </div>
        </swiper-slide>

        <!-- Optional controls -->
        <div class="swiper-pagination"  slot="pagination"></div>

        <!-- 左右箭头和滚动条全部去掉 -->
        <!--<div class="swiper-button-prev" slot="button-prev"></div>
        <div class="swiper-button-next" slot="button-next"></div>
        <div class="swiper-scrollbar"   slot="scrollbar"></div> -->
      </swiper>
  </div>
</template>

<script>
export default {
  name: 'IndexSwiper',
  props: {
    swiperList: Array
  },
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true,
        autoplay: 3000,
        autoplayDisableOnInteraction: true
      }
    }
  }
}
</script>

<style lang="stylus" scoped>
  .wrapper >>> .swiper-pagination-bullet-active
    background: #fff

  .wrapper
    width: 100%
    height: 0
    overflow: hidden
    padding-bottom: 26.66%
    .swiper-image
      width: 100%
</style>
