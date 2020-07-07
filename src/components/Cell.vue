<template>
  <div class="cell" :style="{width: `${dim}px`, height: `${dim}px`}"></div>
</template>

<script>
export default {
  props: ["dim"]
};
</script>

<style>
.cell {
  border-top: 1px solid black;
  border-right: 1px solid black;
  background-color: white;
}
</style>