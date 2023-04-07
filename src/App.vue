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
  <div id="main-wrapper">
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
  </div>
  <p>Site by <a href="https://github.com/ma8642" target="_blank">Marley</a></p>
</template>

<style scoped>
@font-face {
  font-family: 'Kanit';
  src: local('Kanit'), url(./assets/fonts/Kanit/Kanit-Regular.ttf);
}

header {
  width: 100%;
  display: flex;
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

.nav-link {
  text-decoration: none;
  display: flex;
  color: #fcedda;
  opacity: 90%;
}

@media (min-width: 360px) {
  .nav-wrapper {
    width: 100%;
  }

  nav {
    display: flex;
    flex-direction: column;
    width: 100%;
  }

  .nav-link {
    width: 100%;
    padding-top: 30px;
    padding-bottom: 30px;
    display: flex;
    justify-content: center;
    font-size: 2em;
  }
}

@media (min-width: 768px) {
  header {
    justify-content: center;
  }
  .nav-wrapper {
    height: 100%;
    width: 100%;
    display: flex;
  }

  nav {
    height: 100%;
    display: flex;
    flex-direction: row;
    justify-content: end;
    align-items: end;
  }

  .nav-link {
    height: 100%;
    width: 4em;
    padding: 100% 30px 20px 30px;
    justify-content: center;
    align-items: end;
    font-size: 1em;
  }

  .nav-link:hover {
    opacity: 100%;
  }
}
</style>
