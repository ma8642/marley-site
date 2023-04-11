<script lang="ts">
import { RouterLink, RouterView } from 'vue-router'
import SiteTitle from './components/SiteTitle.vue'
export default {
  components: { SiteTitle, RouterLink, RouterView },
  data() {
    return {
      expand: false,
      bgColor: 'none'
    }
  },
  methods: {
    handleTouch(color: string) {
      this.expand = true
      this.bgColor = color
      console.log(this.expand, this.bgColor)
    }
  }
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
      <nav>
        <RouterLink to="/tech" class="nav-link yellow" @click="() => handleTouch('yellow')"
          >TECH</RouterLink
        >
        <RouterLink to="/other" class="nav-link purple" @click="() => handleTouch('purple')"
          >OTHER</RouterLink
        >
        <RouterLink to="/connect" class="nav-link blue" @click="() => handleTouch('blue')"
          >CONNECT</RouterLink
        >
      </nav>
    </div>
    <div :class="{ [`expand-tab ${bgColor}`]: expand === true, tab: true }"><RouterView /></div>
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
  opacity: 100%;
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
    animation: smallStretch 0.5s ease;
    width: 95px;
  }
}

@keyframes smallStretch {
  from {
    width: 90px;
  }
  to {
    width: 95px;
  }
}

.tab {
  width: 0;
}

.expand-tab {
  animation: fillScreen 1s;
  width: 100vw;
}

@keyframes fillScreen {
  from {
    width: 0px;
  }
  to {
    width: 100vw;
  }
}
</style>
