<template>
  <v-app>
    <v-navigation-drawer
        v-model="drawer"
        absolute
        temporary
        dense
        app
    >
      <v-list nav dense>
        <v-list-item-group
            active-class="deep-purple--text text--accent-4">
          <v-list-item class="px-2">
          <v-list-item-avatar>
            <v-img src="../../assets/cat.jpg"></v-img>
          </v-list-item-avatar>
          <v-list-item-title>Alice</v-list-item-title>
          </v-list-item>

          <v-list-item>
            <v-list-item-icon>
              <v-icon>mdi-home</v-icon>
            </v-list-item-icon>
            <v-list-item-title>Home</v-list-item-title>
          </v-list-item>

          <v-list-item>
            <v-list-item-icon>
              <v-icon>mdi-account</v-icon>
            </v-list-item-icon>
            <v-list-item-title>Account</v-list-item-title>

          </v-list-item>
        </v-list-item-group>
      </v-list>
    </v-navigation-drawer>

    <v-app-bar
        color="deep-purple"
        dark
        app
    >
      <v-app-bar-nav-icon @click="drawer = true"></v-app-bar-nav-icon>
      <v-toolbar-title>入侵检测</v-toolbar-title>
      <template v-slot:extension>
        <v-tabs align-with-title grow>
          <v-tab>流量监控</v-tab>
          <v-tab>原始告警</v-tab>
          <v-tab>入侵动作</v-tab>
          <v-tab>添加规则</v-tab>
          <v-tab>添加设备</v-tab>
        </v-tabs>
      </template>
    </v-app-bar>

    <!-- 根据应用组件来调整你的内容 -->
    <v-main>
      <NetWork/>
      <!-- 给应用提供合适的间距 -->
      <v-container fluid>

        <!-- 如果使用 vue-router -->
        <router-view></router-view>
      </v-container>
    </v-main>

    <v-footer app>
      <!-- -->
    </v-footer>
  </v-app>
</template>

<script>
import NetWork from "@/components/Network";

export default {
  name: "Layout",
  components: { NetWork},
  data() {
    return {
      drawer: false,
      items: [
        {title: 'Home', icon: 'mdi-home-city'},
        {title: 'My Account', icon: 'mdi-account'},
        {title: 'Users', icon: 'mdi-account-group-outline'},
      ],
      mini: true,
    }
  }

}
</script>

<style scoped>

</style>
