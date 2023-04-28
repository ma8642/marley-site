<script lang="ts">
import TabView from './TabView.vue'
export default {
  components: { TabView }
}
</script>
<template>
  <TabView>
    <h1>Resume</h1>
    <h2>Summary</h2>
    <h2>Skills</h2>
    <h2>Work Experience</h2>
    <h2>Education</h2>
    <h2>Honors</h2>
  </TabView>
</template>

<style>
@media (min-width: 1024px) {
  h1 {
    font-size: x-large;
  }
  h2 {
    font-size: large;
  }
}
</style>
