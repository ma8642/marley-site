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

header {
  width: 100%;
  display: flex;
  justify-content: center;
}
/* .title-wrapper {
  width: 100%;
} */

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
  width: 4em;
  padding: 100% 30px 20px 30px;
  text-decoration: none;
  display: flex;
  justify-content: center;
  align-items: end;
  color: #fcedda;
  opacity: 90%;
}

.nav-link:hover {
  opacity: 100%;
}

.blue {
  background-color: #11b1cb;
}

.green {
  background-color: #ee4e34;
}

.purple {
  background-color: #8b008b;
}

.yellow {
  background-color: #edc900;
}
</style>
