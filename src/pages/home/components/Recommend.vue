<template>
  <div>
    <div class="title">热销推荐</div>
    <ul>
      <li class="item border-bottom" v-for="item of recommendList" :key="item.id">
        <img class="item-img" :src="item.imgUrl">
        <div class="item-info">
          <p class="item-title">{{ item.title }}</p>
          <p class="item-desc">{{ item.desc }}</p>
          <div class="item-detail">
            <span class="item-unit">¥</span>
            <span class="item-price">{{ item.price }}</span>
            <span>起</span>
            <span class="item-area">{{ item.area }}</span>
          </div>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'Recommend',
  data () {
    return {
      recommendList: [{
        id: '0001',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1702/9b/9b45082b3e38b2fda3.water.jpg_200x200_785628c9.jpg',
        title: '锦绣中华民俗村',
        desc: '56个民族56支花',
        price: 65,
        area: '华侨城'
      }, {
        id: '0002',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1508/2e/d9363ce50a88c8c5ff5a138c67687cd4.water.jpg_200x200_1c15c8f5.jpg',
        title: '深圳野生动物园',
        desc: '这里有优雅和呆萌并存的睫毛精',
        price: 230,
        area: '南山区'
      }, {
        id: '0003',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1902/f2/f2e0213052717f7ca3.water.jpg_200x200_816c1b48.jpg',
        title: '世界之窗',
        desc: '一个下午让你走遍全世界~',
        price: 85,
        area: '华侨城'
      }, {
        id: '0004',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/201405/30/258359fbfa587e26a207cee0ffe39211.jpg_200x200_26567159.jpg',
        title: '观澜山水田园旅游文化园',
        desc: '狂欢无罪，够胆你就来！',
        price: 85,
        area: '南山区'
      }, {
        id: '0005',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1507/64/34362835b4a219af8b36803d31a6380f.water.jpg_200x200_bc5c0452.jpg',
        title: '深圳小梅沙海洋世界',
        desc: '🔥好评如潮，小伙伴热推景点~',
        price: 89.9,
        area: '南山区'
      }]
    }
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/mixins.styl'
  .title
    height: .5rem
    line-height: .5rem
    background: #f5f5f5
    text-indent: .2rem

  .item
    overflow: hidden
    height: 1.9rem
    display: flex
    .item-img
      height: 1.7rem
      width: 1.7rem
      padding: .1rem
    .item-info
      flex: 1
      min-width: 0
      padding: .1rem
      .item-title
        line-height: .54rem
        font-size: .28rem
        ellipsis()
      .item-desc
        line-height: .44rem
        color: #ccc
        font-size: .24rem
        ellipsis()
      .item-detail
        padding-top: .1rem
        font-size: .20rem
        height: .54rem
        margin-bottom: .2rem
        .item-area
          float: right
          margin-right: .3rem
        .item-unit
          color: #ff8300
        .item-price
          color: #ff8300
          font-size: .40rem
</style>
