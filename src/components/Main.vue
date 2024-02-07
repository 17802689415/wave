<template>
  <div class="container">
    <el-scrollbar>

      <el-row>
        <el-col :span="10">
          <div class="left">
            <el-row class="row">
              <el-col :span="4" :offset="1">
                <div class="userTitle"></div>
              </el-col>
              <el-col :span="4">
                <div class="user">
                  DanDan
                </div>

              </el-col>
              <el-col :span="12" :offset="3">
                <Menu></Menu>
              </el-col>
            </el-row>
          </div>
          <div class="left_bottom">

            <div style="width: 100%;">
              <div class="tip">Tips</div>
              <div class="tipDetail">We have <span class="count">5</span> tips waiting</div>
              <el-row>
                <el-col :span="5">
                  <!-- <img src="../assets/jian.svg" height="60"> -->
                  <div class="jia" @click="changeCard"></div>
                </el-col>
                <el-col :span="14">
                  <Card :msg="val" ></Card>
                </el-col>
                <el-col :span="5">
                  <!-- <img src="../assets/jia.svg" height="60"> -->
                  <div class="jian" @click="changeCard"></div>
                </el-col>
              </el-row>
              <div>
                <button class="tipBtn">
                View
              </button>
              </div>
            </div>

          </div>
        </el-col>
        <el-col :span="14">

          <el-row>
            <el-col :span="6" :offset="2">
              <div class="photo">Photo Wall</div>
            </el-col>
            <el-col :span="4" :offset="10">
              <button class="photoBtn">
                View
              </button></el-col>
          </el-row>
          <div class="right">
            <Photo></Photo>
          </div>
        </el-col>
      </el-row>
      <div class="bottom">
        <el-row style="margin-top: 20px;height: 50px;">
          <el-col :span="6">
            <div class="note">Notepad</div>
          </el-col>
          <el-col :span="4" :offset="14">
            <button class="noteBtn">
                View
              </button>
          </el-col>
        </el-row>
        <el-row>
          <el-col :span="6" :offset="1">
            <Date style="margin: auto;"></Date>
          </el-col>
          <el-col :span="17">

          </el-col>
        </el-row>
      </div>


    </el-scrollbar>
  </div>
</template>
<script setup lang="ts">
import Menu from '../components/utilVue/Menu.vue'
import Photo from '../components/utilVue/Photo.vue'
import Card from '../components/utilVue/Card.vue'
import Date from '../components/utilVue/Date.vue'
import {ref} from 'vue'
const val = ref<string>('What did you think of this post?')
const changeCard = () => {
  val.value = 'It have changed'
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
  background-repeat: repeat;
  background-size: contain;
  padding-top: 15px;
  padding-bottom: 15px;
}
.note{
  font-size: 35px;
  color: #D24545;
  margin-left: 30px;
  line-height: 50px;
}
.left {
  width: 90%;
  height: 120px;
  margin: auto;
  border: 0.5rem solid transparent;
  border-radius: 1rem;
  --shadow:
    -.5rem -.5rem 1rem hsl(0 0% 100% / .75),
    .5rem .5rem 1rem hsl(0 0% 50% / .5);
  box-shadow: var(--shadow);
  outline: none;
  box-shadow:
    var(--shadow),
    inset .5rem .5rem 1rem hsl(0 0% 50% / .5),
    inset -.5rem -.5rem 1rem hsl(0 0% 100% / .75);
}
.bottom{
  width: 90%;
  height: 300px;
  margin: auto;
  margin-bottom: 50px;
  border: 0.5rem solid transparent;
  border-radius: 1rem;
  --shadow:
    -.5rem -.5rem 1rem hsl(0 0% 100% / .75),
    .5rem .5rem 1rem hsl(0 0% 50% / .5);
  box-shadow: var(--shadow);
  outline: none;
  box-shadow:
    var(--shadow),
    inset .5rem .5rem 1rem hsl(0 0% 50% / .5),
    inset -.5rem -.5rem 1rem hsl(0 0% 100% / .75);
}

.left_bottom {
  width: 90%;
  height: 450px;
  text-align: center;
  font-size: 30px;
  font-family: 'One', sans-serif;
  margin: auto;
  margin-top: 30px;
  margin-bottom: 35px;
  border: 0.5rem solid transparent;
  border-radius: 50%;
  --shadow:
    -.5rem -.5rem 1rem hsl(0 0% 100% / .75),
    .5rem .5rem 1rem hsl(0 0% 50% / .5);
  box-shadow: var(--shadow);
  outline: none;
  box-shadow:
    var(--shadow),
    inset .5rem .5rem 1rem hsl(0 0% 50% / .5),
    inset -.5rem -.5rem 1rem hsl(0 0% 100% / .75);
  display: flex;
  align-items: center;
  /* 垂直居中 */
  justify-content: center;
}
.tip {
  font-size: 35px;
  color: #83A2FF;
  line-height: 60px;
}

.tipDetail {
  font-size: 20px;
  color: #61A3BA;
  line-height: 30px;
}

.count {
  color: #BE3144;
}
.jia{
  width: 60px;
  height: 60px;
  margin: auto;
  border-radius: 50%;
  border: 5px #80BCBD solid;
  background-image: url(../assets/jia.svg);
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
  cursor: pointer;
}
.jia:hover{
  filter: drop-shadow(0 0 1em #6DA4AA);
}
.jian:hover{
  filter: drop-shadow(0 0 1em #FF9843);
}
.jian{
  width: 60px;
  height: 60px;
  margin: auto;
  border: 5px #FFBB64 solid;
  border-radius: 50%;
  background-image: url(../assets/jian.svg);
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
  cursor: pointer;
}
.right {
  width: 90%;
  height: 550px;
  margin: auto;
  border: 0.5rem solid transparent;
  border-radius: 1rem;
  --shadow:
    -.5rem -.5rem 1rem hsl(0 0% 100% / .75),
    .5rem .5rem 1rem hsl(0 0% 50% / .5);
  box-shadow: var(--shadow);
  outline: none;
  box-shadow:
    var(--shadow),
    inset .5rem .5rem 1rem hsl(0 0% 50% / .5),
    inset -.5rem -.5rem 1rem hsl(0 0% 100% / .75);

  display: flex;
  align-items: center;
  /* 垂直居中 */
  justify-content: center;
}

.row {
  display: flex;
  align-items: center;
  /* 垂直居中 */
  justify-content: center;
  /* 水平居中 */
  height: 100%;
  /* 填充整个父容器的高度 */
}

.user {
  /* border: 1px blue solid; */
  text-align: center;
  font-size: 30px;
  font-weight: 600;
  color: #FF9800;
  text-shadow: 2px 2px 4px red;
}

.userTitle {
  width: 65px;
  height: 65px;
  border-radius: 50%;
  background-image: url(../assets/top.png);
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
}

.photo {
  font-family: 'One', sans-serif;
  font-size: 30px;
  color: #EC8F5E;
  line-height: 40px;
}

.photoBtn {
  --bg: #e74c3c;
  --text-color: #fff;
  position: relative;
  width: 150px;
  border: none;
  background: var(--bg);
  color: var(--text-color);
  padding: 0.8em;
  margin-bottom: 10px;
  font-weight: bold;
  text-transform: uppercase;
  transition: 0.2s;
  border-radius: 5px;
  opacity: 0.8;
  letter-spacing: 1px;
  box-shadow: #c0392b 0px 7px 2px, #000 0px 8px 5px;
  font-family: 'One', sans-serif;
}

.photoBtn:hover {
  opacity: 1;
}

.photoBtn:active {
  top: 4px;
  box-shadow: #c0392b 0px 3px 2px, #000 0px 3px 5px;
}
.tipBtn {
  --bg: #0D9276;
  --text-color: #fff;
  position: relative;
  width: 150px;
  border: none;
  background: var(--bg);
  color: var(--text-color);
  padding: 0.8em;
  margin-top: 15px;
  margin-bottom: 10px;
  font-weight: bold;
  text-transform: uppercase;
  transition: 0.2s;
  border-radius: 5px;
  opacity: 0.8;
  letter-spacing: 1px;
  box-shadow: #12372A 0px 7px 2px, #000 0px 8px 5px;
  font-family: 'One', sans-serif;
}

.tipBtn:hover {
  opacity: 1;
}

.tipBtn:active {
  top: 4px;
  box-shadow: #12372A 0px 3px 2px, #000 0px 3px 5px;
}
.noteBtn {
  --bg: #3468C0;
  --text-color: #fff;
  position: relative;
  width: 150px;
  border: none;
  background: var(--bg);
  color: var(--text-color);
  padding: 0.8em;
  margin-bottom: 10px;
  font-weight: bold;
  text-transform: uppercase;
  transition: 0.2s;
  border-radius: 5px;
  opacity: 0.8;
  letter-spacing: 1px;
  box-shadow: #3652AD 0px 7px 2px, #000 0px 8px 5px;
  font-family: 'One', sans-serif;
}

.noteBtn:hover {
  opacity: 1;
}

.noteBtn:active {
  top: 4px;
  box-shadow: #3652AD 0px 3px 2px, #000 0px 3px 5px;
}
</style>