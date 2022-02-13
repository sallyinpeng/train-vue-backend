<template>
  <el-row :gutter="40" class="line-chart">
    <el-card shadow="hover" style="width:100%;height:280px;margin-left:20px">
      <div ref="lineChart" class="lineChart" style="height:280px" />
    </el-card>
  </el-row>
</template>

<script>
import * as echarts from 'echarts'

const lineChart = {
  legend: {},
  color: ['#2ec7c9', '#b6a2de'],
  xAxis: {
    data: ['周一', '周二', '周三', '周四', '周五', '周六', '周日']
  },
  yAxis: {},
  series: [
    {
      name: '新增用户',
      type: 'bar',
      data: [230, 240, 180, 250, 180, 560, 780],
      barGap: '20%',
      barCategoryGap: '40%'
    },
    {
      name: '活跃用户',
      type: 'bar',
      data: [120, 140, 99, 90, 91, 78, 100]
    }
  ]
}

// const lineChartMessage = {
//   legend: {},
//   color: ['#2ec7c9', '#b6a2de'],
//   xAxis: {
//     data: ['周一', '周二', '周三', '周四', '周五', '周六', '周日']
//   },
//   yAxis: {},
//   series: [
//     {
//       name: '新增',
//       type: 'bar',
//       data: [30, 40, 80, 50, 80, 60, 80],
//       barGap: '20%',
//       barCategoryGap: '40%'
//     },
//     {
//       name: '活跃',
//       type: 'bar',
//       data: [1200, 1400, 990, 900, 910, 780, 1000]
//     }
//   ]
// }
export default {
  name: 'LineChart',
  props: {
    type: {
      type: String,
      required: true
    }
  },
  data() {
    return {

    }
  },
  // watch: { // 点哪个panelgroup就出现哪个对应的charts数据
  //   type(v) {
  //     console.log(v)
  //     switch (v) {
  //       case 'message': {
  //         this.chartLineMyChart.setOption(lineChartMessage)
  //         break
  //       }
  //       default: {
  //         this.chartLineMyChart.setOption(lineChartVisit)
  //       }
  //     }
  //   }
  // },
  //   mounted() {
  //     this.$nextTick(_ => {
  //       this.getEcharts()
  //     })
  //   },
  //   methods: {
  //     getEcharts() {
  //       this.chartLineMyChart = echarts.init(this.$refs.lineChart)
  //       this.chartLineMyChart.setOption(lineChart)
  //     }
  //   }
  // }
  mounted() {
    this.$nextTick(_ => {
      this.chartLineMyChart = echarts.init(this.$refs.lineChart)
      this.chartLineMyChart.setOption(lineChart)
      // this.getEcharts()
    })
  }
  // methods: {
  //   getEcharts() {
  //
  //
  //   }
  // }
}
</script>

<style scoped>

</style>
