<template>
  <div class="tab-container">
    <slot></slot>
  </div>
</template>

<style>
@media (min-width: 1024px) {
  .tab-container {
    height: 100vh;
    display: flex;
    align-items: center;
    overflow-y: auto;
  }
}
</style>
