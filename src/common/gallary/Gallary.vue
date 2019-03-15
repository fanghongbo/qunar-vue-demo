<template>
  <div class="container">
    <div class="wrapper">
      <swiper :options="swiperOptions">
        <swiper-slide>
            <img class="gallary-img" src="http://img1.qunarzz.com/sight/p0/1412/44/570dea8209751ae80caaec0a31242adb.water.jpg_r_800x800_41538bf2.jpg">
        </swiper-slide>
        <swiper-slide>
            <img class="gallary-img" src="http://img1.qunarzz.com/sight/p0/201403/04/71bf72ab808f2f685d8cb9e0192831ff.jpg_r_800x800_01d15b80.jpg">
        </swiper-slide>
        <div class="swiper-pagination"  slot="pagination"></div>
      </swiper>
    </div>
  </div>
</template>

<script>
export default {
  name: 'CommonGallary',
  data () {
    return {
      swiperOptions: {
        pagination: '.swiper-pagination',
        paginationType: 'fraction'
      }
    }
  }
}
</script>

<style lang="stylus" scoped>
  .container >>> .swiper-container
    overflow: inherit
  .container >>> .swiper-wrapper
    vertical-align: middle
    margin-top: 0
    margin-bottom: 0
  .container
    display: flex
    flex-direction: column
    justify-content: center
    z-index: 99
    position: fixed
    left: 0
    right: 0
    top: 0
    bottom: 0
    background: #000
    .wrapper
      .gallary-img
        width: 100%
      .swiper-pagination
        color: #fff
        bottom: -1rem
</style>
