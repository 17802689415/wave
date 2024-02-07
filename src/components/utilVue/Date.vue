<template>
    <div class="content">
        <!-- ===用来制作纸张层叠==== -->
        <div class="form-wrapper">
            <!-- ====制作链条效果=== -->
            <div class="linker">
                <!-- ==== 每个链条 ==== -->
                <span class="ring"></span>
                <span class="ring"></span>
                <span class="ring"></span>
                <span class="ring"></span>
                <span class="ring"></span>
            </div>
            <div style="margin-top: 50px;font-size: 26px;">2024 / 02 / 07 <span style="font-size: 18px;">15:30:55</span></div>
            <div style="margin-top: 15px;color: #FF6868;">From ~ <span>DanDan</span></div>
        </div>
    </div>
</template>
<script setup lang="ts">

</script>
<style scoped>
.content {
    width: 600px;
    height: 100px;
    /* margin: 50px auto; */
}

/*表单容器样式，类似于日历风格*/
.form-wrapper {
    width: 264px;
    height: 160px;
    position: relative;
    border: 1px solid rgb(197, 200, 204);
    background-color: rgb(248, 249, 250);
    text-align: center;
    border-radius: 5px;
    /*圆角*/
    box-shadow: 0 1px 0 rgb(255, 255, 255), 0 2px 0 rgb(197, 200, 204),
        0 3px 0 rgb(255, 255, 255), 0 4px 0 rgb(197, 200, 204);
    /*纸张层叠效果*/
}

/*制作链条顶部背景区域*/
.form-wrapper:before {
    content: "";
    display: block;
    height: 37px;
    border-bottom: 1px solid rgb(197, 200, 204);
    border-radius: 5px 5px 0 0;
    box-shadow: inset 2px 2px 0 rgb(255, 255, 255);
}

/*日历链条和环的制作*/
.form-wrapper .linker {
    position: absolute;
    width: 240px;
    height: 40px;
    top: 18px;
    left: 10px;
}

/*上环*/
.linker .ring {
    position: relative;
    display: inline-block;
    border: 1px solid rgb(163, 164, 167);
    background-color: rgb(220, 222, 225);
    height: 12px;
    width: 12px;
    border-radius: 6px;
    margin-right: 33px;
}

.linker .ring:last-child {
    margin-right: 0;
}

/*下环*/
.linker .ring:before {
    content: "";
    position: absolute;
    bottom: -25px;
    left: -1px;
    border: 1px solid rgb(163, 164, 167);
    background-color: rgb(220, 222, 225);
    height: 12px;
    width: 12px;
    border-radius: 6px;
}

/*中间链条*/
.linker .ring:after {
    content: "";
    position: absolute;
    top: 2px;
    left: 2px;
    width: 6px;
    height: 30px;
    border: 1px solid rgb(202, 202, 202);
    background-color: rgb(255, 255, 255);
    border-radius: 3px;
}</style>