<script setup>
import ChessBoardContainer from './components/ChessBoardContainer.vue'

</script>

<template>
  <div class="page">
      <ChessBoardContainer  />
  </div>
</template>

<style scoped>
.page {
  width: min(100vw - 16px, 100vh - 16px);
  height: min(100vw - 16px, 100vh - 16px);
}
</style>
