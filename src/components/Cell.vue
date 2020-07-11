<template>
  <div
    :class="{
    cell: true, 
    start: state === 1,
    end: state === 2
    }"
    :style="{width: `${dim}px`, height: `${dim}px`}"
  ></div>
</template>

<script>
export default {
  props: ["dim", "state"]
};
</script>

<style>
.cell {
  border-top: 1px solid black;
  border-right: 1px solid black;
  background-color: white;
}
.start {
  background-color: black;
}
.end {
  background-color: green;
}
</style>