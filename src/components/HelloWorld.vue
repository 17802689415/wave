<script setup lang="ts">

</script>

<template>
  <div class="box">
    <div class="wave"></div>
  </div>
    
</template>

<style scoped>
.box{
  position: absolute;
  width: 100vw;
  top: 0;
  left: 0;
  /* border: 1px black solid; */
}

.wave {
  position: relative;
  align-items: center;
  min-height: 100vh;
  background-image: url(../assets/back.png);
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
  overflow: hidden;
}

.wave:before,
.wave:after {
  content: "";
  position: absolute;
  left: 50%;
  min-width: 300vw;
  min-height: 300vw;
  background-color: #fff;
  animation-name: rotate;
  animation-iteration-count: infinite;
  animation-timing-function: linear;
}

.wave:before {
  bottom: 80vh;
  border-radius: 45%;
  animation-duration: 10s;
}

.wave:after {
  bottom: 75vh;
  opacity: 0.5;
  border-radius: 48%;
  animation-duration: 10s;
}

@keyframes rotate {
  0% {
    transform: translate(-50%, 0) rotateZ(0deg);
  }

  50% {
    transform: translate(-50%, 2%) rotateZ(180deg);
  }

  100% {
    transform: translate(-50%, 0) rotateZ(360deg);
  }
}</style>
