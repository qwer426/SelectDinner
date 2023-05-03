<script setup>
import { ref } from 'vue'
const selector = ref(['水餃', '蒸煮食', '蒸煮食對面的排骨飯', '郭台銘', '正忠', '梅乾扣肉', '炒飯／燴飯', '速食', '佳禾', '傻師傅', '鴨肉飯', '羹麵類', '滷味', '其他新的自己想']) 
const startClick = function () {
    const target = document.getElementById(`selectPlay`)
    if (target) {
        target.classList.add('play');
        target.style.transform = 'none';
    }
}
const stopClick = function () {
    const target = document.getElementById(`selectPlay`)
    if (target) {
        const num = Math.floor(Math.random() * 14);
        console.log(num)
        console.log(`${num * 14}%`)
        target.classList.remove('play');
        target.style.transform = `translateY(${-num * 7.14}%)`;
    }
}

</script>
<template>
    <section class="selectGroup">
        <button class="startBtn" @click="startClick">start</button>
        <div id="select">
            <div class="text play" id="selectPlay">
                <div class="selectBox" v-for="i of selector" :key="i">
                    {{ i }}
                </div>
            </div>
        </div>
        <button class="startBtn" @click="stopClick">end</button>
    </section>
</template>


<style scoped>
.selectGroup {
    text-align: center;
}
#select{
    margin: 12px;
    height: 70px;
    border-radius: 4px;
    border: 2px solid gray;
    overflow: hidden;
}
.text {
    background: linear-gradient(LightCoral, Gold, LightSkyBlue, LightCoral);
}
.play {
    animation: resultPlay 1s infinite linear;
}
@keyframes resultPlay {
    100% {
      transform: translateY(-90%)
    }
}
.selectBox{
    font-size: 36px;
    display: flex;
    justify-content: center;
    line-height: 70px;
    color: #fff;
}
.startBtn {
    margin: 0;
    padding: 12px 48px;
    font-size: 20px;
    background: linear-gradient(DarkGray, DimGray);
    color: #fff;
    border-radius: 4px;
    cursor: pointer;
}
</style>