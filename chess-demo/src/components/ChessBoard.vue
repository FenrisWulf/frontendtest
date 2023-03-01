<script>
export default {
    data() {
        return {
            items: Array.apply(null, Array(64)).map((item, idx) => {
                return { row: Math.floor(idx / 8), col: idx % 8 }
            })
        }
    },
    methods: {
        isBlack(row, col) {
            return (row + col) % 2
        },
        handleClick(row, col) {
            this.$emit('handleClick', row, col)
        },
        isHighlighted(row, col) {
            return this.selectedCells.some((cell) => {
                return cell.row === row && cell.col === col
            })
        }
    },
    props: ['selectedCells'],
        
}
</script>

<template>
  <div class="chessboard">
    <div v-for="item in items" style="width: 100%; height: 100%">
      <div class="boardSquare" :class="{black: isBlack(item.row, item.col), highlighted: isHighlighted(item.row, item.col)}" @click="handleClick(item.row, item.col)"></div>
    </div>
  </div>
</template>

<style scoped>
    .chessboard {
        display: grid;
        grid-template-columns: 1fr 1fr 1fr 1fr 1fr 1fr 1fr 1fr;
        width: 100%;
        height: 100%;
    }
    .boardSquare {
        width: 100%;
        height: 100%;
        border: solid 1px black;
    }
    .black {
        background: black
    }
    .highlighted {
        background: yellow;
    }
</style>
