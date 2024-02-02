<template>
  <div class="container">
    <div class="header">

    </div>
    <div class="kittybox">
      <div class="kitty" @click="openLoader">

      </div>
    </div>

    <!-- <img src="../assets/brand-hello-kitty-svgrepo-com.svg"> -->
  </div>
  <div style="margin: auto;">
    <Wel v-if="index" ></Wel>
  </div>
 
</template>
<script setup lang="ts">
import {ref} from 'vue'
// import Loader from './utilVue/Loader.vue';
import Wel from './utilVue/Wel.vue'
const index = ref<boolean>(false)
const openLoader = () => {
  index.value = true
  setTimeout(() => {
    index.value = false
  },3000)
}
</script>
<style scoped>
.container {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  z-index: -10;
  background-image: url(../assets/p2.jpg);
  background-position: center;
  background-repeat: unset;
  background-size: contain;
  /* --color: #E1E1E1;
  background-color: #F3F3F3;
  background-image: linear-gradient(0deg, transparent 24%, var(--color) 25%, var(--color) 26%, transparent 27%, transparent 74%, var(--color) 75%, var(--color) 76%, transparent 77%, transparent),
    linear-gradient(90deg, transparent 24%, var(--color) 25%, var(--color) 26%, transparent 27%, transparent 74%, var(--color) 75%, var(--color) 76%, transparent 77%, transparent);
  background-size: 55px 55px; */
}

.header {
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

.kitty {
  width: 100px;
  height: 100px;
  background-image: url(../assets/kitty.png);
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
  animation: rotate 1s infinite alternate;
  animation-delay: 16s;
}

@keyframes rotate {
  0% {
    transform: rotate(0deg);
  }

  100% {
    transform: rotate(-15deg);
  }
}
.kittybox{
  width: 100px;
  height: 100px;
  transform: translateX(-100px);
  animation-name: walk;
  animation-duration: 6s;
  animation-delay: 10s;
  animation-iteration-count: 1;
  animation-direction: normal;
  animation-fill-mode: forwards;
  animation-timing-function: ease-in-out;
}
@keyframes walk {
  0% {
    transform: translateX(-100px);
  }
  /* 10% {
    transform: translateX(-80px);
  }
  20% {
    transform: translateX(-60px);
  }
  30%{
    transform: translateX(-40px);
  }
  40% {
    transform: translateX(-20px);
  } */
  50%{
    transform: translateX(0px);
  }
  /* 60%{
    transform: translateX(20px);
  }
  70%{
    transform: translateX(40px);
  }
  80%{
    transform: translateX(60px);
  }
  90%{
    transform: translateX(80px);
  } */
  100% {
    transform: translateX(100px);
  }
}
</style>