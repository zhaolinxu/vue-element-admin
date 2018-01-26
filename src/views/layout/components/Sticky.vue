<template>
  <sticky className="sub-navbar">
    <img class="logo" :src="logo" alt="全志一号通">
    <img class="com-logo" :src="logo" alt="">
    <span class="com-name">xx科技有限公司</span>
    <el-button type="info" @click="logout" class="logout">
      <svg-icon icon-class="logout"/>
      注销
    </el-button>
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
</style>
