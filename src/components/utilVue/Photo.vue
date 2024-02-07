<template>
    <div class="options">
        <div v-for="item in imgData" :class="classVal == item.id ? 'optionAct' : 'option'"
            :style="{ backgroundImage: 'url(' + item.path + ')' }">
            <div class="label">
                <div class="icon" @click="changePhoto(item.id)"
                    :style="{ backgroundImage: 'url(src/assets/' + item.id + '.svg)' }">
                </div>

            </div>
        </div>

    </div>
</template>
<script setup lang="ts">
import { ref } from 'vue'
const classVal = ref<number>(1)
interface Img {
    id: number,
    path: string
}
const imgData = ref<Img[]>([
    { id: 1, path: 'src/assets/wave.png' },
    { id: 2, path: 'src/assets/p1.jpg' },
    { id: 3, path: 'src/assets/backImg.jpg' },
    { id: 4, path: 'src/assets/dd.jpg' },
    { id: 5, path: 'src/assets/ll.jpg' },
])
const changePhoto = (val: number) => {
    classVal.value = val
}
</script>
<style scoped>
.options {
    width: 80%;
    height: 90%;
    display: flex;
    align-items: center;
    /* 垂直居中 */
    justify-content: center;
}

.option {
    width: 18%;
    height: 90%;
    margin-left: 6px;
    margin-right: 6px;
    border-radius: 40px;
    /* background-image: url(../../assets/wave.png); */
    background-position: center;
    background-repeat: no-repeat;
    background-size: cover;
    transition: all 1s
}

.optionAct {
    width: 80%;
    height: 90%;
    margin-left: 6px;
    margin-right: 6px;
    border-radius: 40px;
    /* background-image: url(../../assets/wave.png); */
    background-position: center;
    background-repeat: no-repeat;
    background-size: cover;
    transition: all 1s
}

.label {
    height: 60px;
    width: 90%;
    margin: auto;
}

.icon {
    width: 40px;
    height: 40px;
    margin: auto;
    margin-top: 5px;
    border-radius: 50%;
    background-position: center;
    background-repeat: no-repeat;
    background-size: cover;
    border: 2px white solid;
    --shadow:
        -.3rem -.3rem .8rem hsl(0 0% 100% / .75),
        .3rem .3rem .8rem hsl(0 0% 50% / .5);
    box-shadow: var(--shadow);
    outline: none;
    box-shadow:
        var(--shadow),
        inset .3rem .3rem .8rem hsl(0 0% 50% / .5),
        inset -.3rem -.3rem .8rem hsl(0 0% 100% / .75);
}
.icon:hover{
    cursor: pointer;
    transform: scale(1.2);
}
</style>