<template>
  <div>
    <div class="title">周末去哪儿</div>
    <ul>
      <li class="item border-bottom" v-for="item of weekendList" :key="item.id">
        <div class="item-img-wrapper">
          <img class="item-img" :src="item.imgUrl">
        </div>
        <div class="item-info">
          <p class="item-title">{{ item.title }}</p>
          <p class="item-desc">{{ item.desc }}</p>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'Weekend',
  props: {
    weekendList: Array
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
    padding-bottom: .1rem
    .item-img-wrapper
      overflow: hidden
      height: 0
      padding-bottom: 36.5%
      .item-img
        width: 100%
    .item-info
      flex: 1
      min-width: 0
      text-indent: .2rem
      .item-title
        line-height: .50rem
        ellipsis()
      .item-desc
        line-height: .30rem
        font-size: .14rem
        color: #616161
        ellipsis()
</style>
