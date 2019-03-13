<template>
<div>
  <top-header :city="city"></top-header>
  <index-swiper :swiperList="swiperList"></index-swiper>
  <index-icons :iconList="iconList"></index-icons>
  <recommend :recommendList="recommendList"></recommend>
  <weekend :weekendList="weekendList"></weekend>
  <!-- <router-link to="/list" class="home">List</router-link> -->
</div>
</template>

<script>
import TopHeader from './components/Header'
import IndexSwiper from './components/Swiper'
import IndexIcons from './components/Icons'
import Recommend from './components/Recommend'
import Weekend from './components/Weekend'

export default {
  name: 'Home',
  components: {
    TopHeader,
    IndexSwiper,
    IndexIcons,
    Recommend,
    Weekend
  },
  data () {
    return {
      city: '',
      swiperList: [],
      iconList: [],
      recommendList: [],
      weekendList: []
    }
  },
  methods: {
    getInfo () {
      this.$axios.get('/api/index.json').then(this.getInfoSucc)
    },
    getInfoSucc (res) {
      // console.log(res)
      res = res.data
      if (res.ret && res.data) {
        const data = res.data
        this.city = data.city
        this.swiperList = data.swiperList
        this.iconList = data.iconList
        this.recommendList = data.recommendList
        this.weekendList = data.weekendList
      }
    }
  },
  mounted () {
    this.getInfo()
  }
}
</script>

<style>
.home {
  font-size: 60px;
}
</style>
