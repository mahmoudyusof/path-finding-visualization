<template>
  <div id="app">
    <div
      class="grid"
      :style="{
      'grid-template-rows': `repeat(${rows}, ${elDim}px)`,
      'grid-template-columns': `repeat(${cols}, ${elDim}px)`
      }"
    >
      <Cell v-for="i in rows * cols" :key="i" :dim="elDim"></Cell>
    </div>
  </div>
</template>

<script>
import Cell from "./components/Cell.vue";
export default {
  name: "App",
  components: { Cell },
  data() {
    return {
      width: 1200,
      height: 600,
      elDim: 30
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
