<template>

<video src="../assets/mp.mp4" class="bjimg" autoplay loop muted>

</video>
<el-row>
  <el-col>
    <Xin class="xin" :index="index" @click="view"></Xin>
  </el-col>
</el-row>
<el-row>
  <el-col :span="6" :offset="4" class="col">
    <el-avatar src="https://cube.elemecdn.com/0/88/03b0d39583f48206768a7534e55bcpng.png" :size="100" />
  </el-col>
  <el-col :span="6" :offset="4" class="col">
    <el-avatar src="https://cube.elemecdn.com/0/88/03b0d39583f48206768a7534e55bcpng.png" :size="100" />
  </el-col>
</el-row>
<transition name="fade">
  <el-row v-if="index">
    <el-col :span="24">
        <Login class="xin"></Login>
    </el-col>
  </el-row>
</transition>
    
</template>

<script setup lang="ts">
import { ref } from 'vue'
import Xin from './utilVue/Xin.vue'
import Login from './utilVue/Login.vue'
const index = ref<boolean>(false)
const view = () => {
  index.value = !index.value
}
</script> 

<style scoped>
.bjimg {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  z-index: -10;
  object-fit: cover;
}

.col {
  text-align: center;
}

.xin {
  margin: auto;
}

.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.8s ease;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}</style>