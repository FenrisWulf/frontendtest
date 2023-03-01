<script >
export default {
  props: ['selectedCells']
}
</script>

<template>
  <div class="sidebar">
    Sidebar
    <div v-for="item in this.selectedCells">
      <div>Row: {{ item.row  }}, Col: {{ item.col }}</div>
    </div>
  </div>
</template>

<style scoped>
 .sidebar {
    border: solid 1px black;
    min-width: 100px;
  }
</style>
