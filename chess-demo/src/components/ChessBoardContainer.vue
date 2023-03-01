<script>
import ChessBoard from './ChessBoard.vue'
import SideBar from './SideBar.vue'

export default {
  components: {
    ChessBoard,
    SideBar,
  },
  data() {
    return {
        selectedCells: []
    }
  },
  methods: {
    handleClick(row, col) {
        this.selectedCells=[...this.selectedCells, {row, col}]
    }
  }
}

</script>

<template>
  <div class="chessboard-container">
    <div class="chessboard">
      <ChessBoard @handle-click="handleClick" :selected-cells="this.selectedCells"/>
    </div>
    <div class="sidebar">
      <SideBar :selected-cells="this.selectedCells"/>
    </div>
  </div>
</template>

<style scoped>
 
.chessboard-container {
    display: flex;
    align-items: flex-start;
    height: 100%;
    width: 100%;
}
.chessboard {
    width: 100%;
    height: 100%;
    flex-shrink: 0;
}

@media (max-width: 1024px) {
    .chessboard-container {
        flex-direction: column;
    }
}
</style>
