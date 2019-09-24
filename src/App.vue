<template>
  <el-container>
    <el-header class="header" height="100px">
          <h3>Dust&nbsp;&nbsp;仓库管理系统</h3>
          <p>助力中小型企业仓库管理</p>
        </el-header>
    <el-row class="main" :gutter="100">
      <el-col :span="4">
      <el-aside style="width: 15.625rem;">
        <el-row class="tac">
          <el-col>
            <el-menu default-active="2" class="el-menu-vertical-demo" @open="handleOpen" @close="handleClose">
              <el-submenu in dex="1">
                <template slot="title">
                  <i class="el-icon-location"></i>
                  <span>导航一</span>
                </template>
                <el-menu-item-group>
                  <template slot="title">分组一</template>
                  <el-menu-item index="1-1">选项1</el-menu-item>
                  <el-menu-item index="1-2">选项2</el-menu-item>
                </el-menu-item-group>
                <el-menu-item-group title="分组2">
                  <el-menu-item index="1-3">选项3</el-menu-item>
                </el-menu-item-group>
                <el-submenu index="1-4">
                  <template slot="title">选项4</template>
                  <el-menu-item index="1-4-1">选项1</el-menu-item>
                </el-submenu>
              </el-submenu>
              <el-menu-item index="2">
                <i class="el-icon-menu"></i>
                <span slot="title">导航二</span>
              </el-menu-item>
              <el-menu-item index="3" disabled>
                <i class="el-icon-document"></i>
                <span slot="title">导航三</span>
              </el-menu-item>
              <el-menu-item index="4">
                <i class="el-icon-setting"></i>
                <span slot="title">导航四</span>
              </el-menu-item>
            </el-menu>
          </el-col>
        </el-row>
      </el-aside>
      </el-col>
      <el-col :span="16">
      <el-main>
        <router-view />
      </el-main>
      </el-col>
    </el-row>
    <el-footer>
    </el-footer>
  </el-container>
</template>

<script>
  import header from "./components/Login/login.vue";
  export default {
    name: 'App',
    methods: {
      handleOpen(key, keyPath) {
        console.log(key, keyPath);
      },
      handleClose(key, keyPath) {
        console.log(key, keyPath);
      }
    }
  }
</script>

<style>
  .header {
    background-color: #409EFF;
    color: white;
  }

  .el-aside {
    float: left;
  }

  .el-col-12 {
    width: 100%;
  }
</style>
