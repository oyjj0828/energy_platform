<template>
  <div style="height:100%; width:100%;">

    <div style="position:relative; width:100%; height:30px;">
      <div style="position:absolute; width:20%; height:100%; left:75%">
        <el-tabs v-model="activeName" :stretch='true' @tab-click="handleClick">
          <el-tab-pane label="光伏总览" name="光伏总览"></el-tab-pane>
          <el-tab-pane label="数据中心" name="数据中心"></el-tab-pane>
          <el-tab-pane label="实验室楼" name="实验室楼"></el-tab-pane>
        </el-tabs>
      </div>
    </div>

    <div style="position:relative; top:10px; width:100%; height:calc(100%)">
      <div v-if="views[0]" style="width:100%; height:100%;">
        <Overview />
      </div>
      <div v-if="views[1]" style="width:100%; height:100%;">
        <DataCenter />
      </div>
      <div v-if="views[2]" style="width:100%; height:100%;">
        <Lab />
      </div>
    </div>
  </div>
</template>

<script>
import Overview from '@/components/GuangFU/Overview';
import Lab from '@/components/GuangFU/Lab';
import DataCenter from '@/components/GuangFU/DataCenter'

export default {
  components: {
    Overview,
    DataCenter,
    Lab,
  },
  data() {
    return {
      activeName: '光伏总览',
      views: [true, false, false]
    }
  },
  methods: {
    handleClick() {
      switch (this.activeName){
        case '光伏总览': {
          this.views = [true, false, false];
          break;
        }
        case '数据中心': {
          this.views = [false, true, false];
          break;
        }
        case '实验室楼': {
          this.views = [false, false, true];
          break;
        }
      }
    },
  },
}
</script>