<template>
  <div class="header">
    <div class="header-left">
      <div class="iconfont back-icon">&#xe624;</div>
    </div>
    <div class="header-input">
      <span class="iconfont search-icon">&#xe632;</span>输入城市/景点/游玩主题
  </div>
    <div class="header-right">城市
      <span class="iconfont arrow-icon">&#xe64a;</span>
    </div>
  </div>
</template>

<script>
export default {
  name: 'TopHeader'
}
</script>

<!-- scoped限制css只对局部这个组件有效 -->
<!-- css导入其他css方式 -->
<!-- @import '~@/assets/styles/varibles.styl' -->

<!--在build/wabpack.base.conf.js中定义的styles 别名之后,可以直接使用别名的方式导入其他样式 -->

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .header
    display: flex
    height: .86rem
    line-height: .86rem
    background: $bgColor
    color: #fff

    .header-left
      width: .64rem
      float: left

      .back-icon
        font-size: .4rem
        text-align: center

    .header-right
      width: 1.24rem
      float: right
      text-align: center

      .arrow-icon
        font-size: .24rem
        padding-left: -.4rem

    .header-input
      flex: 1
      height: .64rem
      line-height: .64rem
      margin-top: .12rem
      margin-left: .12rem
      background: #fff
      border-radius: .1rem
      color: #ccc

      .search-icon
        padding-left: .1rem
        padding-right: .1rem

</style>
