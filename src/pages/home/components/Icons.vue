<template>
  <div class="icons">
    <swiper :options="swiperOption">  <!-- 轮播效果 -->
      <swiper-slide v-for="(page, index) of pages" :key="index">
        <div class="icon" v-for="item of page" :key="item.id">
          <div class="icon-img">
            <img class="icon-img-content" :src="item.imgUrl">
            <p class="icon-desc">{{ item.desc }}</p>
          </div>
        </div>
      </swiper-slide>
<!--       <swiper-slide>
        <div class="icon">
          <div class="icon-img">
            <img class="icon-img-content" src="http://img1.qunarzz.com/piao/fusion/1804/5a/13ceb38dcf262f02.png">
            <p class="icon-desc">一日游</p>
          </div>
        </div>
      </swiper-slide> -->
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'IndexIcons',
  props: {
    iconList: Array
  },
  data () {
    return {
      swiperOption: {
        autoplay: false
      }
    }
  },
  computed: {
    pages () {
      const pages = []
      this.iconList.forEach((item, index) => {
        const page = Math.floor(index / 8)
        if (!pages[page]) {
          pages[page] = []
        }
        pages[page].push(item)
      })
      return pages
    }
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  @import '~styles/mixins.styl'
  .icons >>> .swiper-slide
    height: 0
    padding-bottom: 50%

  .icons
    margin-top: .1rem

    .icon
      width: 25%
      height: 0
      position: relative
      overflow: hidden
      padding-bottom: 25%
      float: left

      .icon-img
        position: absolute
        bottom: .60rem
        top: 0
        left: 0
        right: 0
        padding: .1rem
        box-sizing: border-box
        text-align: center

        .icon-img-content
          height: 100%
          margin: 1px auto
          display: block

      .icon-desc
        color: $darkTextColor
        ellipsis()

</style>
