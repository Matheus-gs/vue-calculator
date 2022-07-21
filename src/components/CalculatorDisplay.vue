<template>
  <div class="display">{{ displayValue }}</div>
</template>

<script>
export default {
  props: ["displayValue"],
};
</script>

<style>
.display {
  grid-column: span 4;
  /* background: #0004; */
  display: flex;
  justify-content: flex-end;
  align-items: center;
  padding: 20px;
  font-size: 2em;
  overflow: hidden;
}
</style>