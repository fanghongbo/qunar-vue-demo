<template>
<div>
  <top-header></top-header>
  <index-swiper></index-swiper>
  <!-- <router-link to="/list" class="home">List</router-link> -->
</div>
</template>

<script>
import TopHeader from './components/Header'
import IndexSwiper from './components/Swiper'
export default {
  name: 'Home',
  components: {
    TopHeader,
    IndexSwiper
  }
}
</script>

<style>
.home {
  font-size: 60px;
}
</style>
