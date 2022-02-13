<template>
  <el-row :gutter="40" class="panel-group">
    <el-col v-for="item in panelGroup" :key="item.title" :xs="12" :sm="12" :lg="6" class="card-panel-col">
      <div class="card-panel" @click="$emit('change', item.type)">
        <div class="card-icon">
          <i :class="['icon', item.icon]" />
        </div>
        <div class="card-text">
          <div class="text-title">{{ item.title }}</div>
          <div class="text-num">{{ item.num }}</div>
        </div>
      </div>
    </el-col>
  </el-row>
</template>

<script>
export default {
  name: 'PanelGroup',
  data() {
    return {
      panelGroup: [
        {
          type: 'visits',
          icon: 'el-icon-user-solid',
          title: 'New Visits',
          num: '102,400'
        },
        {
          type: 'message',
          icon: 'el-icon-s-goods',
          title: 'Messages',
          num: '81,212'
        },
        {
          type: 'purchase',
          icon: 'el-icon-picture-outline-round',
          title: 'Purchases',
          num: '9,280'
        },
        {
          type: 'shopping',
          icon: 'el-icon-s-help',
          title: 'Shopping',
          num: '13,600'
        }

      ]
    }
  },
  mounted() {
    setTimeout(_ => {
      this.$emit('change', this.panelGroup[0].type)
    }, 500)
  }
}
</script>

<style lang="less" scoped>
.panel-group {
  .card-panel {
    height: 108px;
    cursor: pointer;
    font-size: 12px;
    position: relative;
    overflow: hidden;
    color: #666;
    background: #fff;
    box-shadow: 4px 4px 40px rgb(0 0 0 / 5%);
    border-color: rgba(0, 0, 0, 0.05);
    margin-bottom: 20px;
  }

  .card-icon {
    float: left;
    //margin: 14px 0 0 14px;
    padding: 16px;
    transition: all 0.38s ease-out;
    border-radius: 6px;

    /deep/ .icon {
      font-size: 600%;
      color: #40c9c6;
    }
  }

  .card-text {
    float: right;
    font-weight: bold;
    margin: 26px;
    margin-left: 0;

    .text-title {
      line-height: 18px;
      color: rgba(0, 0, 0, 0.45);
      font-size: 16px;
      margin-bottom: 12px;
    }

    .text-num {
      font-size: 20px;
    }
  }
}
</style>
