<template>
  <div id="app">
    <div
      class="grid"
      :style="{
      'grid-template-rows': `repeat(${rows}, ${elDim}px)`,
      'grid-template-columns': `repeat(${cols}, ${elDim}px)`
      }"
    >
      <Cell v-for="(obj, i) in grid" :key="i" :index="i" :dim="elDim" :state="obj.state"></Cell>
    </div>
  </div>
</template>

<script>
import Cell from "./components/Cell.vue";
export default {
  name: "App",
  components: { Cell },
  created() {
    for (let i = 0; i < this.rows * this.cols; i++) {
      if (i == this.cols * 1 + 0) {
        this.$set(this.grid, i, { state: 1 });
      } else if (i === this.cols * this.rows - 1) {
        this.$set(this.grid, i, { state: 2 });
      } else {
        this.$set(this.grid, i, { state: 0 });
      }
    }
  },
  data() {
    return {
      width: 1200,
      height: 600,
      elDim: 30,
      grid: []
    };
  },
  computed: {
    rows() {
      return Math.floor(this.height / this.elDim);
    },
    cols() {
      return Math.floor(this.width / this.elDim);
    }
  }
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
#app {
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: #eee;
  height: 100vh;
}
.grid {
  display: grid;
  border-bottom: 1px solid black;
  border-left: 1px solid black;
}
</style>
