<template>
<div>
  <top-header></top-header>
  <!-- <router-link to="/list" class="home">List</router-link> -->
</div>
</template>

<script>
import TopHeader from './components/Header'
export default {
  name: 'Home',
  components: {
    TopHeader
  }
}
</script>

<style>
.home {
  font-size: 60px;
}
</style>
