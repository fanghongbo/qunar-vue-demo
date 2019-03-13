<template>
<div>
  <top-header></top-header>
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
import { mapState } from 'vuex'

export default {
  name: 'Home',
  components: {
    TopHeader,
    IndexSwiper,
    IndexIcons,
    Recommend,
    Weekend
  },
  computed: {
    ...mapState(['city'])
  },
  data () {
    return {
      swiperList: [],
      iconList: [],
      recommendList: [],
      weekendList: [],
      lastCity: ''
    }
  },
  methods: {
    getInfo () {
      // this.$axios.get('/api/index.json?city=' + this.$store.state.city).then(this.getInfoSucc)
      this.$axios.get('/api/index.json?city=' + this.city).then(this.getInfoSucc)
    },
    getInfoSucc (res) {
      res = res.data
      if (res.ret && res.data) {
        const data = res.data
        this.swiperList = data.swiperList
        this.iconList = data.iconList
        this.recommendList = data.recommendList
        this.weekendList = data.weekendList
      }
    }
  },
  mounted () {
    this.getInfo()
    // this.lastCity = this.$store.state.city
    this.lastCity = this.city
  },
  activated () {
    // if (this.lastCity !== this.$store.state.city) {
    //   this.lastCity = this.$store.state.city
    //   this.getInfo()
    // }
    if (this.lastCity !== this.city) {
      this.lastCity = this.city
      this.getInfo()
    }
  }
}
</script>

<style>
.home {
  font-size: 60px;
}
</style>
