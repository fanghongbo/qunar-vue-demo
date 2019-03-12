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
  props: {
    recommendList: Array
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
