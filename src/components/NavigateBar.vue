<template>
  <v-navigation-drawer
    v-model="layout.primaryDrawer.model"
    :clipped="layout.primaryDrawer.clipped"
    :floating="layout.primaryDrawer.floating"
    :mini-variant="layout.primaryDrawer.mini"
    :permanent="layout.primaryDrawer.type === 'permanent'"
    :temporary="layout.primaryDrawer.type === 'temporary'"
    app
    overflow
  >
    <v-list dense nav>
      <v-list-item v-for="item in links" :key="item.title" link @click="toPage(item.link)">
        <!-- <v-list-item-icon></v-list-item-icon> -->
        <v-list-item-content>
          <v-list-item-title>{{item.title}}</v-list-item-title>
        </v-list-item-content>
      </v-list-item>
    </v-list>
    <v-divider></v-divider>
  </v-navigation-drawer>
</template>
<script>
import global from "../global/Global";
export default {
  name: "NavigateBar",
  data: () => {
    return {
      layout: global.layout,
      links: [
        {
          title: "Home",
          link: "/"
        },
        {
          title: "About",
          link: "/about"
        },
        {
          title: "Layout Settings",
          link: "/layout"
        }
      ],
      routing: false
    };
  },
  methods: {
    toPage: function(targetPath) {
      //禁止同时多次点击和重复访问相同地址
      if (!this.routing && this.$router.history.current.path != targetPath) {
        this.routing = true;
        this.$router
          .push({
            path: targetPath
          })
          .then(() => {
            this.routing = false;
          })
          .catch(err => {
            console.log(err);
            this.routing = false;
          });
      }
    }
  }
};
</script>