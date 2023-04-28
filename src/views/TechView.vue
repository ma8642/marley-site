<script lang="ts">
import TabView from './TabView.vue'
import ResumeItem from '../components/ResumeItem.vue'
export default {
  components: { ResumeItem, TabView }
}
</script>
<template>
  <TabView>
    <div class="resume-container">
      <h1>Summary</h1>
      <p>
        Frontend engineer with 4 years of professional experience across the stack. Alum of Bard
        College '17, hackNY '17, and StartupBus '22. NY -> Berlin.
      </p>
      <h1>Skills</h1>
      <p>
        Javascript, Typescript, HTML, CSS, React, Vue, NextJs, D3, Cypress, Storybook, CircleCI,
        PostgresQL.
      </p>
      <h1>Experience</h1>
      <ResumeItem />
      <ResumeItem />

      <h2>Education</h2>
      <h2>Honors</h2>
    </div>
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
  .resume-container {
    height: 100%;
    width: 90%;
  }
}
</style>
