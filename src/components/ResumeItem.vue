<script setup lang="ts"></script>

<template>
  <div class="resumeItem">
    <div class="heading">
      <h2>title</h2>
      <p>location</p>
      <p>date</p>
    </div>
    <ul>
      <li>thing 1</li>
      <li>thing 2</li>
    </ul>
  </div>
</template>

<style scoped>
@media (min-width: 1024px) {
  h2 {
    font-size: large;
  }
  p {
    font-size: medium;
  }
  .heading {
    display: flex;
    justify-content: space-between;
  }
}
</style>
