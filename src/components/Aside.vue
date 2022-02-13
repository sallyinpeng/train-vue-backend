<template>
  <el-scrollbar wrap-class="scrollbar-wrapper">
    <el-menu
      active-text-color="#409eff"
      text-color="#ccc"
      background-color="#304156"
      :collapse="isCollapse"
    >
      <el-menu-item v-for="item in hasNoChild" :key="item.name" :index="item.name">
        <i :class="item.icon" />
        <span slot="title">{{ item.name }}</span>
      </el-menu-item>
      <el-submenu v-for="item in hasChildren" :key="item.name" :index="item.name">
        <template slot="title">
          <i :class="item.icon" />
          <span slot="title">{{ item.name }}</span>
        </template>
        <el-menu-item-group>
          <el-menu-item
            v-for="subItem in item.children"
            :key="subItem.name"
            :index="subItem.name"
          >
            <i :class="subItem.icon" />
            <span slot="title">{{ subItem.name }}</span>
          </el-menu-item>
        </el-menu-item-group>
      </el-submenu>
    </el-menu>
  </el-scrollbar>
</template>

<script>
export default {
  name: 'Aside',
  data() {
    return {
      // isCollapse: false,
      menu: [{
        name: 'Dashboard',
        icon: 'el-icon-s-home'
      }, {
        name: 'Documentation',
        icon: 'el-icon-notebook-2'
      }, {
        name: 'Permission',
        icon: 'el-icon-s-goods',
        children: [{
          name: 'Page Permission'
        }, {
          name: 'Directive Permission'
        }, {
          name: 'Role Permission'
        }]
      }, {
        name: 'Icon',
        icon: 'el-icon-star-on'
      }, {
        name: 'Table',
        icon: 'el-icon-s-fold',
        children: [{
          name: 'Dynamic Table'
        }, {
          name: 'Drag Table'
        }, {
          name: 'Inline Edit'
        }, {
          name: 'Complex Table'
        }]
      }, {
        name: 'Example',
        icon: 'el-icon-help',
        children: [{
          name: 'Create Article',
          icon: 'el-icon-info'
        }, {
          name: 'Article List',
          icon: 'el-icon-s-order'
        }]
      }, {
        name: 'Tab',
        icon: 'el-icon-s-platform'
      }, {
        name: 'Error Pages',
        icon: 'el-icon-s-help',
        children: [{
          name: '401'
        }, {
          name: '404'
        }]
      }, {
        name: 'Excel',
        icon: 'el-icon-s-data',
        children: [{
          name: 'Export Excel'
        }, {
          name: 'Export Selected'
        }, {
          name: 'Merge Header'
        }, {
          name: 'Upload Excel'
        }]
      }, {
        name: 'Zip',
        icon: 'el-icon-s-claim',
        children: [{
          name: 'Export Zip'
        }]
      }, {
        name: 'PDF',
        icon: 'el-icon-s-ticket'
      }, {
        name: 'Theme',
        icon: 'el-icon-s-management'
      }, {
        name: 'Clipboard',
        icon: 'el-icon-s-opportunity'
      }, {
        name: 'External Link',
        icon: 'el-icon-s-release'
      }
      ]
    }
  },
  computed: {
    hasNoChild() {
      return this.menu.filter((item) => !item.children)
    },
    hasChildren() {
      return this.menu.filter((item) => item.children)
    },
    isCollapse() {
      return this.$store.state.tab.isCollapse
    }
  },
  methods: {
    // handleOpen (key, keyPath) {
    //   console.log(key, keyPath)
    // },
    // handleClose (key, keyPath) {
    //   console.log(key, keyPath)
    // }
  }
}
</script>

<style lang="less" scoped>
.el-menu:not(.el-menu--collapse) {
  width: 200px;
  min-height: 400px;
}

.el-scrollbar {
  height: 100%;

  .scrollbar-wrapper {
    overflow-x: hidden !important;
  }
}
</style>
