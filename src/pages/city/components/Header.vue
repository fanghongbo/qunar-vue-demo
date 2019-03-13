<template>
<div class="header">
  <div class="header-left">
    <router-link to="/">
      <div class="iconfont back-icon">&#xe624;</div>
    </router-link>
  </div>
  <div class="header-title">城市选择</div>
</div>
</template>

<script>
export default {
  name: 'CityHeader'
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .header
    display: flex
    height: $headerHeight
    line-height: $headerHeight
    background: $bgColor
    text-align: center
    font-size: .32rem
    color: #fff
    .header-left
      width: .64rem
      height: .86rem
      text-align: center
      .back-icon
        color: #fff
        font-size: .4rem
    .header-title
      flex: 1
      margin-left: - $headerHeight
</style>
