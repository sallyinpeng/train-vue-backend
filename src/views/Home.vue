<template>
  <el-container>
    <el-aside width="auto">
      <Aside />
    </el-aside>
    <el-container>
      <el-header>
        <Header />
      </el-header>
      <el-main>
        <router-view />
      </el-main>
    </el-container>
  </el-container>
</template>

<script>
// @ is an alias to /src
import Aside from '../components/Aside.vue'
import Header from '../components/Header.vue'

export default {
  name: 'Home',
  components: {
    Aside,
    Header
  }
}
</script>

<style lang="less" scoped>
.el-container {
  height: 100%;
  width: 100%;

  .el-aside {
    height: 100vh;
    background-color: rgb(48 65 86);
  }

  .el-header {
    padding: 0;
  }
}
</style>
