<template>
  <div class="menu">
    <!-- 头部 -->
    <header class="header">头部</header>
    <!-- 内容 -->
    <div>
      <!-- 侧边栏 -->
      <navBar class="nav-bar"></navBar>
      <!-- 内容 -->
      <div class="content-bar">
        <tagsView></tagsView>
        <appMain></appMain>
      </div>
    </div>
  </div>
</template>

<script>
import navBar from "@/components/layOut/navBar"
import tagsView from "@/components/layOut/tagsView"
import appMain from "@/components/layOut/appMain"
export default {
  name: "HelloWorld",
  components: {
    navBar,
    tagsView,
    appMain
  },
  data () {
    return {
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.header{
  height: 80px;
  width: 100%;
  color: aliceblue;
  background: linear-gradient(to bottom right, blue, rgb(87, 133, 231));
  margin: 0;
  padding: 0;
}
.nav-bar{
  z-index:500;
  display: inline-block;
  position: absolute;
  left: 0;
}
.content-bar{
  z-index:1;
  display: inline-block;
}
</style>
