<template>
    <div class="like-dislike-container">
        <div class="tool-box">
            <button class="btn-close">×</button>
        </div>
        <p class="text-content">{{ props.msg }}</p>
        <div class="icons-box">
            <CheckBox></CheckBox>
        </div>
    </div>
</template>
<script setup lang="ts">
import CheckBox from './CheckBox.vue';
const props = defineProps(['msg'])
</script>
<style scoped>
.like-dislike-container {
    --dark-grey: #353535;
    --middle-grey: #767676;
    --lightest-grey: linear-gradient(#fafafa, #ebebeb);
    --shadow: 0 5px 15px 0 #00000026;
    --shadow-active: 0 5px 5px 0 #00000026;
    --border-radius-main: 10px;
    --border-radius-icon: 50px;
    position: relative;
    display: flex;
    text-align: center;
    flex-direction: column;
    align-items: center;
    cursor: default;
    color: var(--dark-grey);
    opacity: .9;
    margin: auto;
    padding: 2rem;
    font-weight: 600;
    background: var(--lightest-grey);
    max-width: max-content;
    border-radius: var(--border-radius-main);
    box-shadow: var(--shadow);
    transition: .2s ease all;
}

.like-dislike-container:hover {
    box-shadow: var(--shadow-active);
}

.like-dislike-container .tool-box {
    position: absolute;
    display: flex;
    align-items: center;
    justify-content: center;
    width: 2.5rem;
    height: 2.5rem;
    top: 0;
    right: 0;
    border-radius: var(--border-radius-main);
}

.like-dislike-container .btn-close {
    display: flex;
    align-items: center;
    justify-content: center;
    text-align: center;
    width: .8rem;
    height: .8rem;
    color: transparent;
    font-size: 0;
    cursor: pointer;
    background-color: #ff000080;
    border: none;
    border-radius: var(--border-radius-main);
    transition: .2s ease all;
}

.like-dislike-container .btn-close:hover {
    width: 1rem;
    height: 1rem;
    font-size: 1rem;
    color: #ffffff;
    background-color: #ff0000cc;
    box-shadow: var(--shadow-active);
}

.like-dislike-container .btn-close:active {
    width: .9rem;
    height: .9rem;
    font-size: .9rem;
    color: #ffffffde;
    --shadow-btn-close: 0 3px 3px 0 #00000026;
    box-shadow: var(--shadow-btn-close);
}

.like-dislike-container .text-content {
    margin-bottom: 1rem;
    font-size: 18px;
    line-height: 1.6;
    cursor: default;
}

.like-dislike-container .icons-box {
    display: flex;
}
</style>