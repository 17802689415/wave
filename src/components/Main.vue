<template>
<div class="container">
  <div class="header"></div>
</div>
</template>
<script setup lang="ts">

</script>
<style scoped>
.container {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  z-index: -10;
  --color: #E1E1E1;
  background-color: #F3F3F3;
  background-image: linear-gradient(0deg, transparent 24%, var(--color) 25%, var(--color) 26%, transparent 27%,transparent 74%, var(--color) 75%, var(--color) 76%, transparent 77%,transparent),
      linear-gradient(90deg, transparent 24%, var(--color) 25%, var(--color) 26%, transparent 27%,transparent 74%, var(--color) 75%, var(--color) 76%, transparent 77%,transparent);
  background-size: 55px 55px;
}
.header{
  width: 90%;
  height: 50px;
  border-radius: 25px;
  border: 2px #FFC5C5 solid;
  margin: auto;
  margin-top: 15px;
  box-shadow: 5px 5px 5px -1px #31304D; 
  background-color: #FFC5C5;
  /* 2B2A4C  161A30  FFC5C5*/
}
</style>