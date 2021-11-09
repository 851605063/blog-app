<template>
  <el-card>
    <h1 class="me-author-name">王青尘</h1>
    <div class="me-author-description">
      <span><i class="el-icon-location-outline"></i> &nbsp;浙江&绍兴</span>
      <span><i class="me-icon-job"></i> &nbsp;YYDS</span>
    </div>
    <div class="me-author-tool">
      <el-tooltip :content="wx.title" placement="top" effect="light">
        <i class="iconfont icon-wxweixin" ></i>
      </el-tooltip>
      <el-popover
        placement="top"
        width="181"
        height="180"
        v-model="visible">
        <img src="../../assets/img/gzhmini.jpg" height="180" width="181"/>
        <i  :title="gzh.title" class="iconfont icon-wxweixingongzhonghao" slot="reference"></i>
      </el-popover>

    </div>
  </el-card>

</template>

<script>
  export default {
    name: 'CardMe',
    data() {
      return {
        wx: {title: '微信号：qfgk16', message: 'qfgk16'},
        gzh: {
          title: '微信公众号：王青尘',
          message: '微信搜：王青尘'
        },
        visible:false,
      }
    },
    methods: {
      showTool(tool) {
        this.$message({
          duration: 0,
          showClose: true,
          dangerouslyUseHTMLString: true,
          message: '<strong>' + tool.message + '</strong>'
        });
      },

    }
  }
</script>

<style scoped>
  .me-author-name {
    text-align: center;
    font-size: 30px;
    border-bottom: 1px solid #5FB878;
  }

  .me-author-description {
    padding: 8px 0;
  }

  .me-icon-job {
    padding-left: 16px;
  }

  .me-author-tool {
    text-align: center;
    padding-top: 10px;
  }

  .me-author-tool i {
    cursor: pointer;
    padding: 4px 10px;
    font-size: 30px;
  }
</style>
