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
    <div class="title-wrapper">
      <SiteTitle />
    </div>
  </header>
  <div class="nav-wrapper">
    <nav v-on:click="handleTouch">
      <RouterLink to="/" class="nav-link">TECH</RouterLink>
      <RouterLink to="/about" class="nav-link">ACTING</RouterLink>
      <RouterLink to="/about" class="nav-link">OTHER</RouterLink>
      <RouterLink to="/about" class="nav-link">CONNECT</RouterLink>
    </nav>
  </div>
  <div v-if="touched === true"><RouterView /></div>
</template>

<style scoped>
@font-face {
  font-family: 'Kanit';
  src: local('Kanit'), url(./assets/fonts/Kanit/Kanit-Regular.ttf);
}

.nav-wrapper {
  height: 90%;
  display: flex;
  align-items: end;
}

.nav-link {
  padding: 20px 30px 20px 30px;
}
</style>
