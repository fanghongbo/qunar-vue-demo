<template>
<div>
  <top-header></top-header>
  <index-swiper></index-swiper>
  <index-icons></index-icons>
  <recommend></recommend>
  <!-- <router-link to="/list" class="home">List</router-link> -->
</div>
</template>

<script>
import TopHeader from './components/Header'
import IndexSwiper from './components/Swiper'
import IndexIcons from './components/Icons'
import Recommend from './components/Recommend'
export default {
  name: 'Home',
  components: {
    TopHeader,
    IndexSwiper,
    IndexIcons,
    Recommend
  }
}
</script>

<style>
.home {
  font-size: 60px;
}
</style>
