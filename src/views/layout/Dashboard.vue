<template>
  <div class="dashboard">
    <panel-group @change="type = $event" />
    <el-row>
      <line-chart :type="type" />
    </el-row>
  </div>
</template>

<script>
import PanelGroup from '../../components/Dashboard/PannelGroup'
import LineChart from '../../components/Dashboard/LineChart'

export default {
  name: 'Dashboard',
  components: {
    PanelGroup,
    LineChart
  },
  data() {
    return {
      type: ''
    }
  }
}
</script>

<style lang="less" scoped>
.dashboard {
  padding: 32px;
  background-color: #f0f2f5;
  position: relative;
}
</style>
