<template>
    <v-app-bar :clipped-left="primaryDrawer.clipped" app>
        <v-app-bar-nav-icon
          v-if="primaryDrawer.type !== 'permanent'"
          @click.stop="primaryDrawer.model = !primaryDrawer.model"
        ></v-app-bar-nav-icon>
        <v-toolbar-title>{{primaryDrawer.title?primaryDrawer.title:"Elphen"}}</v-toolbar-title>
        <v-toolbar-items></v-toolbar-items>
      </v-app-bar>
</template>
<script>
import global from '../global/Global';
export default {
    name:"TopBar",
    data:()=>{
        return{
            primaryDrawer:global.layout.primaryDrawer
        }
    }
}
</script>