<script setup></script>

<template>
  <div class="boxGroup">
    <div class="box">
      <div class="boxHeader"><p>biggus dikkus</p></div>
      <div class="boxContent"><p>hoho the one piece is real</p></div>
      <div class="boxFooter"><p>this is coppyrightus</p></div>
    </div>
  </div>
</template>

<style scoped>
.box {
  display: grid;
  grid-template-columns: 1fr;
  grid-template-rows: auto 2fr auto;
  grid-column-gap: 0px;
  grid-row-gap: 0px;
  width: 500px;
  height: 300px;
  border: 2px solid black;
  box-shadow: #83c5a7 0px 54px 55px, #83c5a7 0px -12px 30px, #83c5a7 0px 4px 6px,
    #83c5a7 0px 12px 13px, #83c5a7 0px -3px 5px;
}

.boxHeader {
  grid-row: 1;
  border-bottom: 2px ridge #7c3a58;
}

.boxContent {
  grid-row: 2;
  border-bottom: 2px ridge #7c3a58;
}
.boxFooter {
  grid-row: 3;
}
</style>

<script>
export default {};
</script>
