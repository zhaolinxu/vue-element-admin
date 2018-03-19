<template>
  <scroll-bar>
       <img class="logo" :src="logo" alt="全志一号通">
    <el-menu mode="vertical" :default-active="$route.path" :collapse="isCollapse" >
      <sidebar-item :routes="permission_routers"></sidebar-item>
    </el-menu>
  </scroll-bar>
</template>

<script>
import { mapGetters } from 'vuex'
import SidebarItem from './SidebarItem'
import ScrollBar from '@/components/ScrollBar'
import logo from '@/assets/logo.png'

export default {
  components: { SidebarItem, ScrollBar },
  computed: {
    ...mapGetters([
      'permission_routers',
      'sidebar'
    ]),
    isCollapse() {
      return !this.sidebar.opened
    }
  },data() {
      return {
        logo,
      }
    }
}
</script>
