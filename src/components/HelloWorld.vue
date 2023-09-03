<template>
  <div class="menu">
    <!-- 头部 -->
    <header class="header">头部</header>
    <!-- 内容 -->
    <div>
      <!-- 侧边栏 -->
      <navBar></navBar>
      <!-- 内容 -->
      <div>
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
}
</style>
