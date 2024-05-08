<template>
  <div class="background_img">
    <head>
      <meta charset="utf-8">
      <title>蒙电综合能源管理平台</title>
    </head>
    <div class="head" style="z-index: 10;">
      <h1 style="font-size: xx-large;">蒙电综合能源管理平台</h1>
      <div class="time" id="showTime">{{ currentTime }}</div>
      <div style="position:absolute; right:5px; width:150px; top:5px; height:35px;">
        <img src="@/assets/全屏.png" style="position:absolute; width:30px; height:30px; right:100px; cursor: pointer;" @click="handleZoom"/>
        <div style="position:absolute; right:0; width:90px ;height:inherit; cursor: pointer;"  @click="handleLogInfo">
          <img src="@/assets/头像.png" style="position:absolute; height:30px; width:30px; right:60px; top:0;">
          <div style="position:absolute; height:inherit; width:50px; right:5px; top:-2.5px; font-size: 16px; 
          color:rgb(161, 200, 240); display: flex; justify-content: center; align-items: center;">
            admin
          </div>
        </div>
      </div>
    </div>

    <div style="position:relative; top:5px; width:100%; height:60px;">
      <div style="position:absolute; width:35%; height:100%; left:60%">
        <el-tabs v-model="activeName" :stretch='true' @tab-click="handleClick">
          <el-tab-pane label="总览" name="总览"></el-tab-pane>
          <el-tab-pane label="微电网" name="微电网"></el-tab-pane>
          <el-tab-pane label="光伏" name="光伏"></el-tab-pane>
          <el-tab-pane label="储能" name="储能"></el-tab-pane>
          <el-tab-pane label="供冷供热" name="供冷供热"></el-tab-pane>
          <el-tab-pane label="水系统" name="水系统"></el-tab-pane>
          <el-tab-pane label="负荷" name="负荷"></el-tab-pane>
        </el-tabs>
      </div>
    </div>

    <div style="position:relative; top:10px; width:100%; height:calc(100% - 130px )">
      <div v-if="views[0]" style="width:100%; height:100%;">
        <ZongLan />
      </div>
      <div v-else-if="views[1]" style="width:100%; height:100%;">
        <WeiDianWang/>
      </div>
      <div v-else-if="views[2]" style="width:100%; height:100%;">
        <GuangFu />
      </div>
      <div v-else-if="views[3]" style="width:100%; height:100%;">
        <ChuNeng/>
      </div>
      <div v-else-if="views[4]" style="width:100%; height:100%;">
        <GongLengGongRe/>
      </div>
      <div v-else-if="views[5]" style="width:100%; height:100%;">
        <ShuiXiTong/>
      </div>
      <div v-else-if="views[6]" style="width:100%; height:100%;">
        <FuHe/>
      </div>
    </div>
  </div>
</template>

<script>
import ZongLan from '@/components/ZongLan.vue';
import WeiDianWang from '@/components/WeiDianWang.vue';
import GuangFu from '@/components/GuangFu.vue';
import ChuNeng from '@/components/ChuNeng.vue';
import GongLengGongRe from '@/components/GongLengGongRe.vue';
import ShuiXiTong from '@/components/ShuiXiTong.vue';
import FuHe from '@/components/FuHe.vue';


export default {
  components: {
    ZongLan,
    WeiDianWang,
    GuangFu,
    ChuNeng,
    GongLengGongRe,
    ShuiXiTong,
    FuHe,
  },
  data() {
    return {
      currentTime: '',
      activeName: '总览',
      views:[true, false, false, false, false, false, false],  // 总览 微电网 光伏 储能 供冷供热 水系统 负荷
    };
  },
  computed: {

  },
  mounted() {
    this.updateTime();
    setInterval(() => {
      this.updateTime();
      // this.fetchDataAndUpdate();    
    }, 1000);
  },
  methods: {
    handleLogInfo(){  // 显示用户信息

    },
    handleZoom(){  // 实现全屏功能
      let element = document.documentElement;
      if (!document.fullscreenElement) {
        if (element.requestFullscreen) {
          element.requestFullscreen();
        } else if (element.mozRequestFullScreen) { /* Firefox */
          element.mozRequestFullScreen();
        } else if (element.webkitRequestFullscreen) { /* Chrome, Safari and Opera */
          element.webkitRequestFullscreen();
        } else if (element.msRequestFullscreen) { /* IE/Edge */
          element.msRequestFullscreen();
        }
      } else {
        if (document.exitFullscreen) {
          document.exitFullscreen();
        } else if (document.mozCancelFullScreen) { /* Firefox */
          document.mozCancelFullScreen();
        } else if (document.webkitExitFullscreen) { /* Chrome, Safari and Opera */
          document.webkitExitFullscreen();
        } else if (document.msExitFullscreen) { /* IE/Edge */
          document.msExitFullscreen();
        }
      }
    },
    handleClick() {
      switch (this.activeName){
        case '总览': {
          this.views = [true, false, false, false, false, false, false];
          break;
        }
        case '微电网': {
          this.views = [false, true, false, false, false, false, false];
          break;
        }
        case '光伏': {
          this.views = [false, false, true, false, false, false, false];
          break;
        }
        case '储能': {
          this.views = [false, false, false, true, false, false, false];
          break;
        }
        case '供冷供热': {
          this.views = [false, false, false, false, true, false, false];
          break;
        }
        case '水系统': {
          this.views = [false, false, false, false, false, true, false];
          break;
        }
        case '负荷': {
          this.views = [false, false, false, false, false, false, true];
          break;
        }
      }
    },
    updateTime() {
      const dt = new Date();
      const y = dt.getFullYear();
      const mt = dt.getMonth() + 1;
      const day = dt.getDate();
      const h = dt.getHours();
      const m = dt.getMinutes();
      const s = dt.getSeconds();
      this.currentTime = `${y}/${this.Appendzero(mt)}/${this.Appendzero(day)} ${this.Appendzero(h)}:${this.Appendzero(m)}:${this.Appendzero(s)}`;
    },
    Appendzero(obj) {
      return obj < 10 ? `0${obj}` : obj;
    },
  }
}
</script>

<style scoped>
@import '../public/css/comon0.css';

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  height: inherit;
}

::v-deep .el-tabs__item.is-active {  /* 被选中时 */
  color: #00b44e;  
  font-size:16px;
  font-weight:bold;
}

::v-deep .el-tabs__item {  /* 未被选中时 */
  color: #009bba; 
  font-size:16px;
  font-weight:bold;
}

</style>
