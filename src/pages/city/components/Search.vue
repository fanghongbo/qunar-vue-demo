<template>
<div>
  <div class="search">
    <input class="search-input" v-model="keyword" type="text" name="" placeholder="输入城市名或者拼音">
  </div>
  <div class="search-content" ref="content" v-show="keyword">
    <ul>
      <li class="search-item border-bottom" v-for="item of list" :key="item.id">{{ item.name }}</li>
      <li class="search-item border-bottom" v-show="!list.length">没有找到匹配内容</li>
    </ul>
  </div>
</div>
</template>

<script>
import Bscroll from 'better-scroll'
export default {
  name: 'CitySearch',
  props: {
    cities: Object
  },
  data () {
    return {
      keyword: '',
      timer: null,
      list: []
    }
  },
  mounted () {
    this.scroll = new Bscroll(this.$refs.content)
  },
  watch: {
    keyword () {
      if (this.timer) {
        clearTimeout(this.timer)
      }
      if (!this.keyword) {
        this.list = []
        return
      }
      this.timer = setTimeout(() => {
        const result = []
        for (let item in this.cities) {
          this.cities[item].forEach((value) => {
            if (value.spell.indexOf(this.keyword) > -1 || value.name.indexOf(this.keyword) > -1) {
              result.push(value)
            }
          })
        }
        this.list = result
      })
    }
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .search
    height: .72rem
    background: $bgColor
    text-align: center
    padding:0 .1rem
    .search-input
      box-sizing: border-box
      width: 100%
      height: .62rem
      padding:0 1rem
      line-height: .62rem
      text-align: center
      border-radius: .06rem
      color: #666
  .search-content
    z-index: 1
    position: absolute
    overflow: hidden
    top: 1.58rem
    left: 0
    right: 0
    bottom: 0
    background: #eee
    .search-item
      line-height: .62rem
      text-indent: .2rem
      color: #666
      background: #fff
</style>
