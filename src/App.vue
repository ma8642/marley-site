<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
import SiteTitle from './components/SiteTitle.vue'
let touched: boolean = false
function handleTouch() {
  console.log(touched)
  touched = true
}
</script>

<template>
  <header>
    <div class="wrapper">
      <SiteTitle />
    </div>
  </header>
  <div>
    <nav v-on:click="handleTouch">
      <RouterLink to="/">TECH</RouterLink>
      <RouterLink to="/about">ACTING</RouterLink>
      <RouterLink to="/about">OTHER</RouterLink>
      <RouterLink to="/about">CONNECT</RouterLink>
    </nav>
  </div>
  <div v-if="touched === true"><RouterView /></div>
</template>

<style scoped>
@font-face {
  font-family: 'Kanit';
  src: local('Kanit'), url(./assets/fonts/Kanit/Kanit-Regular.ttf);
}
</style>
