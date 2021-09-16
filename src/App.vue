<template>
  <div id="app">
    <div class="left-container">
      <div style="height:64px"></div>
      <Menu theme="dark" style="width:100%">
        <MenuItem name="2">
          <Icon type="ios-paper" />
          查询管理</MenuItem
        >
        <Submenu name="1">
          <template slot="title">
            <Icon type="ios-paper" />
            路线管理
          </template>
          <MenuItem name="1-1">干线管理</MenuItem>
          <MenuItem name="1-2">直线管理</MenuItem>
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
