<script lang="ts">
import { RouterLink, RouterView } from 'vue-router'
import SiteTitle from './components/SiteTitle.vue'
export default {
  components: { SiteTitle, RouterLink, RouterView },
  data() {
    return {
      expand: -1,
      bgColor: 'none'
    }
  },
  methods: {
    handleTouch(tabIndex: number, color: string) {
      if (this.expand === tabIndex) {
        // if use clicks an open tab, close it
        this.expand = -1
      } else {
        this.expand = tabIndex
        this.bgColor = color
      }
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
        <RouterLink to="/tech" class="nav-link yellow" @click="() => handleTouch(0, 'yellow')"
          >TECH</RouterLink
        >
        <div :class="{ [`expand-tab ${bgColor}`]: expand === 0, tab: expand != 0, hi: true }">
          <RouterView />
        </div>
        <RouterLink to="/other" class="nav-link purple" @click="() => handleTouch(1, 'purple')"
          >OTHER</RouterLink
        >
        <div :class="{ [`expand-tab ${bgColor}`]: expand === 1, tab: expand != 1, bi: true }">
          <RouterView />
        </div>
        <RouterLink to="/connect" class="nav-link blue" @click="() => handleTouch(2, 'blue')"
          >CONNECT</RouterLink
        >
        <div :class="{ [`expand-tab ${bgColor}`]: expand === 2, tab: expand != 2, gi: true }">
          <RouterView />
        </div>
      </nav>
    </div>
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
  display: none;
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
