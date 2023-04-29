<script lang="ts">
export default {
  props: ['role', 'company', 'location', 'dates', 'highlights']
}
</script>

<template>
  <div class="resumeItem">
    <div class="heading">
      <div>
        <h2>{{ role }}</h2>
      </div>
      <div class="secondary-details">
        <h3>{{ company }}</h3>
        <h3>{{ location }}</h3>
        <h3>{{ dates }}</h3>
      </div>
    </div>
    <ul>
      <li v-for="highlight in highlights" :key="highlight.id">{{ highlight.text }}</li>
    </ul>
  </div>
</template>

<style scoped>
@media (min-width: 1024px) {
  h2 {
    font-size: large;
  }
  h3 {
    font-weight: 200;
  }
  p {
    font-size: medium;
  }
  .heading {
    display: flex;
    flex-direction: column;
    justify-content: flex-start;
  }

  .secondary-details {
    display: flex;
    justify-content: space-between;
  }
}
</style>
