<template>
  <div>
    <div class="banner">
      <img class="banner-img" src="http://img1.qunarzz.com/sight/p0/1702/9b/9b45082b3e38b2fda3.water.jpg_600x330_33015f04.jpg">
      <div class="banner-info">
        <div class="banner-desc">锦绣中华民俗村(AAAAA景区)</div>
        <div class="banner-num">
          <span class="iconfont banner-icon">&#xe67b;</span>
          39
      </div>
      </div>
    </div>
    <!-- <common-gallary></common-gallary> -->
  </div>
</template>

<script>
import CommonGallary from 'common/gallary/Gallary'
export default {
  name: 'BannerDetail',
  components: {
    CommonGallary
  }
}
</script>

<style lang="stylus" scoped>
  .banner
    position: relative
    overflow: hidden
    height: 0
    padding-bottom: 55%
    .banner-img
      width: 100%
    .banner-info
      display: flex
      position: absolute
      left: 0
      right: 0
      bottom: 0
      color: #fff
      line-height: .8rem
      padding-right: .2rem
      background-image: linear-gradient(top, rgba(0,0,0,0), rgba(0,0,0,.8))
      .banner-desc
        flex: 1
        text-indent: .2rem
        font-size: .36rem
      .banner-num
        margin-top: .2rem
        padding: 0 .4rem
        height: .4rem
        font-size: .22rem
        line-height: .4rem
        border-radius: .2rem
        background: rgba(0,0,0,.6)
        .banner-icon
          font-size: .22rem
</style>
