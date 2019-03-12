<template>
<div>
  <top-header></top-header>
  <index-swiper></index-swiper>
  <index-icons></index-icons>
  <!-- <router-link to="/list" class="home">List</router-link> -->
</div>
</template>

<script>
import TopHeader from './components/Header'
import IndexSwiper from './components/Swiper'
import IndexIcons from './components/Icons'
export default {
  name: 'Home',
  components: {
    TopHeader,
    IndexSwiper,
    IndexIcons
  }
}
</script>

<style>
.home {
  font-size: 60px;
}
</style>
