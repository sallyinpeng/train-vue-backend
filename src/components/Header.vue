<template>
  <div class="header">
    <div class="header-left">
      <el-button plain size="mini" @click="handleMenu"><i class="el-icon-menu" /></el-button>
      <!--      <el-breadcrumb>-->
      <!--        <el-breadcrumb-item :to="{ path: '/' }">首页</el-breadcrumb-item>-->
      <!--        <el-breadcrumb-item :to="current.path" v-if="current">{{ current.label }}</el-breadcrumb-item>-->
      <!--      </el-breadcrumb>-->
    </div>
    <div class="header-right">
      <el-dropdown trigger="click">
        <span class="el-dropdown-link">
          <el-avatar src="https://cube.elemecdn.com/0/88/03b0d39583f48206768a7534e55bcpng.png" />
        </span>
        <el-dropdown-menu slot="dropdown">
          <el-dropdown-item>个人中心</el-dropdown-item>
          <el-dropdown-item>退出</el-dropdown-item>
        </el-dropdown-menu>
      </el-dropdown>
    </div>
  </div>
</template>

<script>
// import { mapState } from 'vuex'

export default {
  name: 'Header',
  data() {
    return {}
  },
  methods: {
    handleMenu() {
      this.$store.commit('collapseMenu')
    }
  }
  // computed: {
  //   ...mapState({
  //     current: state => state.tab.currentMenu
  //   })
  // }
}
</script>

<style lang="less" scoped>
.header {
  height: 60px;
  background: #fff;
  display: flex;
  justify-content: space-between;
  border-bottom: 1px solid #f0f2f5;

  .header-left {
    padding-left: 15px;
    padding-top: 15px;
  }

  .header-right {
    padding-top: 10px;
    padding-right: 15px;
  }
}
</style>
