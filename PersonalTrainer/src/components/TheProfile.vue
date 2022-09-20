<script setup></script>

<template>
  <div class="boxGroup">
    <div class="box"></div>
  </div>
</template>

<style scoped>
.box {
  display: grid;
  grid-template-columns: 1fr;
  grid-template-rows: repeat(3, 1fr);
  grid-column-gap: 0px;
  grid-row-gap: 0px;
  width: 500px;
  height: 300px;
  border: 2px solid black;
  box-shadow: #83c5a7 0px 54px 55px, #83c5a7 0px -12px 30px, #83c5a7 0px 4px 6px,
    #83c5a7 0px 12px 13px, #83c5a7 0px -3px 5px;
}

.boxGroup {
}
</style>

<script>
export default {};
</script>
