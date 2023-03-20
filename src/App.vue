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
      <RouterLink to="/" class="nav-link yellow">TECH</RouterLink>
      <RouterLink to="/about" class="nav-link green">ACTING</RouterLink>
      <RouterLink to="/about" class="nav-link purple">OTHER</RouterLink>
      <RouterLink to="/about" class="nav-link blue">CONNECT</RouterLink>
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
  height: 100%;
}

nav {
  height: 100%;
  display: flex;
  align-items: end;
}

.nav-link {
  height: 100%;
  padding: 100% 30px 20px 30px;
  text-decoration: none;
  display: flex;
  align-items: end;
  color: #f0f0f1;
  opacity: 90%;
}

.nav-link:hover {
  opacity: 100%;
}

.blue {
  background-color: #00d4a1;
}

.green {
  background-color: #ed5300;
}

.purple {
  background-color: #7151fe;
}

.yellow {
  background-color: #edc900;
}
</style>
