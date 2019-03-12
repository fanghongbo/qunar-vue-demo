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
  data () {
    return {
      swiperOption: {
        autoplay: false
      },
      dataList: [{
        id: '0001',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
        desc: '热门景点'
      }, {
        id: '0002',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1804/5a/13ceb38dcf262f02.png',
        desc: '一日游'
      }, {
        id: '0003',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1804/ff/fdf170ee89594b02.png',
        desc: '滑雪季'
      }, {
        id: '0004',
        imgUrl: 'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20191/0334cf5430b9b5505fd79e2b8d7e8670.png',
        desc: '爬长城'
      }, {
        id: '0005',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/6c/9e54a8540fee0102.png',
        desc: '故宫'
      }, {
        id: '0006',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/e3/67df61427c8e1302.png',
        desc: '茶馆相声'
      }, {
        id: '0007',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/bd/9f7b9b2b60c1502.png',
        desc: '踏青赏花'
      }, {
        id: '0008',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/47/c2b659e048b11602.png',
        desc: '遛娃儿'
      }, {
        id: '0009',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/ab/6f7d6e44963c9302.png',
        desc: '泡温泉'
      }, {
        id: '00010',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/76/eb88861d78fb9902.png',
        desc: '动植物园'
      }]
    }
  },
  computed: {
    pages () {
      const pages = []
      this.dataList.forEach((item, index) => {
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
