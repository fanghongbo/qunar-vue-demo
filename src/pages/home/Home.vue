<template>
<div>
  <top-header></top-header>
  <index-swiper></index-swiper>
  <index-icons></index-icons>
  <recommend></recommend>
  <weekend></weekend>
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
  }
}
</script>

<style>
.home {
  font-size: 60px;
}
</style>
