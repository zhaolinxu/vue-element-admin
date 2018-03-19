<template>
  <sticky className="sub-navbar">
<!--    <img class="logo" :src="logo" alt="全志一号通">-->
<!--    <img class="com-logo" :src="logo" alt="">-->
<!--    <span class="com-name">xx科技有限公司</span>b-->
   <div class="topMenu">
       <el-button type="text" class="active">工作台</el-button>
       <el-button type="text">文档中心</el-button>
       <el-button type="text">常见问题</el-button>
       <el-button type="text">资源下载</el-button>
       <el-button type="text">开发工具</el-button>
       <el-button type="text">技术支持</el-button>
       <el-button type="text">统计分析</el-button>
   </div>
   <el-dropdown>
  <span class="el-dropdown-link">
    下拉菜单<i class="el-icon-arrow-down el-icon--right"></i>
  </span>
  <el-dropdown-menu slot="dropdown">
    <el-dropdown-item>黄金糕</el-dropdown-item>
    <el-dropdown-item>狮子头</el-dropdown-item>
    <el-dropdown-item>螺蛳粉</el-dropdown-item>
    <el-dropdown-item disabled>双皮奶</el-dropdown-item>
    <el-dropdown-item divided>蚵仔煎</el-dropdown-item>
  </el-dropdown-menu>
</el-dropdown>
  </sticky>

</template>


<script>
  import Sticky from '@/components/Sticky'
  import logo from '@/assets/logo.png'

  export default {
    name: 'sticky-demo',
    components: { Sticky },
    data() {
      return {
        time: '',
        url: '',
        logo,
        platforms: ['a-platform'],
        platformsOptions: [
          { key: 'a-platform', name: 'platformA' },
          { key: 'b-platform', name: 'platformB' },
          { key: 'c-platform', name: 'platformC' }
        ],
        pickerOptions: {
          disabledDate(time) {
            return time.getTime() > Date.now()
          }
        }
      }
    },
    methods: {
      logout() {
        this.$store.dispatch('LogOut').then(() => {
          location.reload()// In order to re-instantiate the vue-router object to avoid bugs
        })
      }
    }
  }
</script>

<style scoped>
  .components-container div {
    margin: 10px;
  }

  .time-container {
    display: inline-block;
  }
    .sub-navbar{height: 100px;}
</style>
