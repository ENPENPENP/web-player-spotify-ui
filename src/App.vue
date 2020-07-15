<template>
  <div id="app">
    <v-app id="sandbox"><!-- 盒子模型容器 -->
      <navigate-bar /><!-- 左侧导航栏 -->
      <top-bar /> <!-- 顶部应用栏 -->
      <v-main><!-- 内容主容器 -->
        <v-container fluid>
          <router-view />
        </v-container>
      </v-main>
      <control-bar /><!-- 底部控制栏 -->
    </v-app>
  </div>
</template>
<script>
import controlBar from "@/components/ControlBar";
import navigateBar from "@/components/NavigateBar";
import topBar from "@/components/TopBar";
export default {
  name: "app",
  data: () => ({}),
  components: {
    "control-bar": controlBar,
    "navigate-bar": navigateBar,
    "top-bar": topBar
  },
  methods: {
  }
};
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
