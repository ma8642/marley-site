<script lang="ts">
import TabView from './TabView.vue'
export default {
  components: { TabView }
}
</script>
<template>
  <TabView>
    <h1>Email</h1>
    <h2>Linkedin</h2>
    <h2>Shlinkedin</h2>
  </TabView>
</template>

<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}
</style>
