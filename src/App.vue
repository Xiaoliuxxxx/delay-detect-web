<template>
  <div id="app">
    <div class="left-container">
      <div style="height:64px"></div>
      <Menu theme="dark" style="width:100%">
        <Submenu name="1">
          <template slot="title">
            <Icon type="ios-paper" />
            内容管理
          </template>
          <MenuItem name="1-1">文章管理</MenuItem>
          <MenuItem name="1-2">评论管理</MenuItem>
          <MenuItem name="1-3">举报管理</MenuItem>
        </Submenu>
        <Submenu name="2">
          <template slot="title">
            <Icon type="ios-people" />
            用户管理
          </template>
          <MenuItem name="2-1">新增用户</MenuItem>
          <MenuItem name="2-2">活跃用户</MenuItem>
        </Submenu>
        <Submenu name="3">
          <template slot="title">
            <Icon type="ios-stats" />
            统计分析
          </template>
          <MenuGroup title="使用">
            <MenuItem name="3-1">新增和启动</MenuItem>
            <MenuItem name="3-2">活跃分析</MenuItem>
            <MenuItem name="3-3">时段分析</MenuItem>
          </MenuGroup>
          <MenuGroup title="留存">
            <MenuItem name="3-4">用户留存</MenuItem>
            <MenuItem name="3-5">流失用户</MenuItem>
          </MenuGroup>
        </Submenu>
      </Menu>
    </div>
    <div class="right-container">
      <div class="header"></div>
      <router-view />
    </div>
  </div>
</template>

<script>
export default {
  name: "App"
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  height: 100vh;
  width: 100%;
  display: flex;
}
.left-container {
  width: 200px;
  height: 100%;
  color: #fff;
  background: #515a6e;
  display: flex;
  flex-direction: column;
}
.header {
  width: 100%;
  height: 64px;
  box-sizing: border-box;
  border-bottom: 1px solid #dcdfe6;
}
.right-container {
  flex: 1;
  height: 100%;
  background: #f5f7f9;
}
</style>
