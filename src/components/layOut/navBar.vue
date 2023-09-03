<!-- 导航栏 -->
<template>

  <el-menu default-active="1-4-1" class="el-menu-vertical-demo" @open="handleOpen" @close="handleClose"
    :collapse="isCollapse" background-color="#545c64" text-color="#fff" active-text-color="#ffd04b">
    <div @click="isCollapseBtn">
      <i class="el-icon-s-fold" v-if="isCollapse"></i>
      <i class="el-icon-s-operation" v-else></i>
    </div>
    <div v-for="(item,index) in menuList">
      <el-submenu :index="index">
        <template slot="title">
          <i class="el-icon-location"></i>
          <span>{{ item.menuName }}</span>
        </template>
        <el-menu-item-group v-for="(ele,ind) in item.Children">
          <el-menu-item :index="ind">{{ ele.menuName }}</el-menu-item>
        </el-menu-item-group>
      </el-submenu>
    </div>
  </el-menu>

</template>

<script>
  export default {
    name: 'navBar',
    data() {
      return {
        isCollapse: true,
        menuList: [
          {
            menuName: '页面1', meta: { show: true },
            Children: [{ menuName: "子页面1" }, { menuName: "子页面2" }]
          }
        ],
      };
    },
    methods: {
      isCollapseBtn() {
        this.isCollapse = !this.isCollapse

      },
      handleOpen(key, keyPath) {
        console.log(key, keyPath);
      },
      handleClose(key, keyPath) {
        console.log(key, keyPath);
      }
    }
  }
</script>
<style scoped>
  .el-menu-vertical-demo:not(.el-menu--collapse) {
    width: 200px;
    min-height: 400px;
  }
</style>