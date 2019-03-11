<template>
  <div class="wrapper">
    <!-- <swiper :options="swiperOption"> -->
    <swiper>
        <swiper-slide>
          <div>
            <img class="swiper-image" src="@/assets/swiper-img/1.jpg">
          </div>
        </swiper-slide>
        <swiper-slide>
          <div>
          <img class="swiper-image" src="@/assets/swiper-img/2.jpg">
          </div>
        </swiper-slide>
        <swiper-slide>
          <div>
          <img class="swiper-image" src="@/assets/swiper-img/3.jpg">
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
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true
      },
      swiperList: [{
        id: '0001',
        imgUrl: '/assets/swiper-img/1.jpg'
      }, {
        id: '0002',
        imgUrl: '/assets/swiper-img/2.jpg'
      }, {
        id: '0003',
        imgUrl: '/assets/swiper-img/3.jpg'
      }]
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
