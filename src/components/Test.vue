<template>
    <div id="bg">
        
    </div>
    <div id="bg_mask">
        
    </div>
    <main>
        <div class="title">小宝的爱情博物馆</div>
        <div class="middle">我们已经相恋</div>
        <div class="time"> {{ time }} -</div>
        <Login class="log"></Login>
    </main>
    
    <div id="spotlight"><Input class="input"></Input></div>
</template>

<script setup lang="ts">
import Login from './utilVue/Login.vue'
import Input from './utilVue/Input.vue'
import { ref,onMounted } from 'vue'
// 目标日期时间
const targetDate = new Date('2023-07-21T22:00:00');
// 使用响应式变量存储计算结果
const days = ref(0);
const time = ref('');
onMounted(() => {
    update()
    setInterval(() => {
        update();
    }, 1000); // 每秒更新一次时间
})
// 计算时间差并格式化为字符串
const formatTimeDiff = (diff:any) => {
    const seconds = Math.floor(diff / 1000) % 60;
    const minutes = Math.floor(diff / 1000 / 60) % 60;
    const hours = Math.floor(diff / 1000 / 60 / 60) % 24;
    const days = Math.floor(diff / 1000 / 60 / 60 / 24);
    return `${days}天 ${hours.toString().padStart(2, '0')}时 ${minutes.toString().padStart(2, '0')}分 ${seconds.toString().padStart(2, '0')}秒`;
};
// 监听计算结果的变化
const update = () => {
    const now = new Date();
    const diff = targetDate.getTime() - now.getTime();
    days.value = Math.floor(diff / 1000 / 60 / 60 / 24);
    time.value = formatTimeDiff(diff);
}

</script>
<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Montserrat:wght@500&display=swap");

main {
    position: relative;
    color: crimson;
    mix-blend-mode: color-burn;
    z-index: 0;
}

.title {
    line-height: 150px;
    font-size: 60px;
    margin-left: 20px;
}
.middle{
    margin-top: 60px;
    font-size: 39px;
    margin-left: 60px;
}
.time{
    font-size: 30px;
    margin-left: 60px;
}
.input{
    margin-top: 80vh;
    margin-left: 70vw;
}
#bg,
#bg_mask {
    position: absolute;
    top: 0;
    right: 0;
    bottom: 0;
    left: 0;
    margin: calc(var(--blur) * -1);

    background-image: url(https://images.unsplash.com/photo-1532153955177-f59af40d6472?crop=entropy&cs=srgb&fm=jpg&ixid=M3wzMjM4NDZ8MHwxfHJhbmRvbXx8fHx8fHx8fDE2OTg2NTgxNzR8&ixlib=rb-4.0.3&q=100&w=2000);
    background-size: cover;
    background-repeat: no-repeat;
    background-position: center;
    z-index: 0;
}

#spotlight,
#bg_mask {
    background-color: rgba(0, 0, 0, 0.6);
    mask: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='546.133' height='448' viewBox='-20 -20 552 460'%3E%3Cdefs%3E%3Cfilter id='filter'%3E%3CfeGaussianBlur stdDeviation='10' /%3E%3C/filter%3E%3C/defs%3E%3Cpath fill='black' filter='url(%23filter)' d='M257 112c.28-12.93 5.99-29.47 11.75-41C300.62 7.27 376.04-17.2 440 12.31c33.67 15.54 60.35 48.63 68.77 84.69 4.11 17.63 3.43 29.19 3.23 47-.23 19.09-8.22 50.95-14.95 69C468.4 289.85 404.82 349.11 333 386.26L278 412c-4.6 1.84-17.87 7.79-22 7.79-4.18 0-20.12-7.02-25-8.99-21.1-8.51-41.08-18.56-61-29.5C95.65 340.48 30.02 274.83 7.88 191 .49 162.99-.33 146.56 0 118c.17-14.32 6.36-34.21 12.75-47C19.82 56.86 29.21 43.78 41 33.17c49.22-44.3 123.25-44.16 173-.88 10.52 9.15 20.7 22.36 27.22 34.71 6.75 12.8 13.46 30.42 13.78 45h2Z'/%3E%3C/svg%3E"),
        linear-gradient(#fff 0 0);
    mask-size: var(--size), 100%;
    mask-position: calc(var(--x) - var(--size) / 2) calc(var(--y) - var(--size) / 2 * 0.65),
        left top;
    mask-repeat: no-repeat;
    mask-mode: alpha;
}

#spotlight {
    position: fixed;
    top: 0;
    left: 0;
    height: 100vh;
    width: 100vw;
    -webkit-mask-composite: destination-out;
    mask-composite: exclude;
    z-index: 1;
}
</style>