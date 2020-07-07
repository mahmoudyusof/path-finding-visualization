<template>
  <div id="app">
    <div
      class="grid"
      :style="{
      'grid-template-rows': `repeat(${rows}, ${elDim}px)`,
      'grid-template-columns': `repeat(${cols}, ${elDim}px)`
      }"
    >
      <div
        v-for="i in rows * cols"
        :key="i"
        class="cell"
        :style="{width: `${elDim}px`, height: `${elDim}px`}"
      ></div>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      width: 800,
      height: 600,
      elDim: 60
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
  background-color: white;
  display: grid;
}
.cell {
  border: 1px solid black;
}
</style>
