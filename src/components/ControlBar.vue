<template>
  <v-footer :inset="!layout.footer.cover" color="layout.themes.spotifyColor.black.hex" app min-height="15vh">
   <v-row align="center" style="min-height:15vh">
      <v-img src="../assets/default_cover.jpg" min-width="1vh" min-height="1vh" aspect-ratio="1" max-height="10vh" max-width="10vh" style=""></v-img>
   </v-row>
  </v-footer>
</template>
<script>
import global from "../global/Global";
export default {
  name: "ControlBar",
  data: () => {
    return {
      layout:global.layout,
    };
  }
};
</script>