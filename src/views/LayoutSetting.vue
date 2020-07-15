<template>
  <v-row align="center" justify="center">
    <v-col cols="10">
      <v-card>
        <v-card-text>
          <v-row>
            <v-col cols="12" md="6">
              <span>Drawer</span>
              <v-radio-group v-model="primaryDrawer.type" column>
                <v-radio
                  v-for="drawer in drawers"
                  :key="drawer"
                  :label="drawer"
                  :value="drawer.toLowerCase()"
                  primary
                ></v-radio>
              </v-radio-group>
              <v-switch v-model="primaryDrawer.clipped" label="Clipped" primary></v-switch>
              <v-switch v-model="primaryDrawer.floating" label="Floating" primary></v-switch>
              <v-switch v-model="primaryDrawer.mini" label="Mini" primary></v-switch>
            </v-col>
            <v-col cols="12" md="6">
              <span>Footer</span>
              <v-switch v-model="footer.cover" label="Cover" primary></v-switch>
            </v-col>
          </v-row>
        </v-card-text>
      </v-card>
    </v-col>
  </v-row>
</template>
<script>
import global from '../global/Global';
export default {
  name: "LayoutSetting",
  data: () => ({
    drawers: global.layout.drawers,
    primaryDrawer: global.layout.primaryDrawer,
    footer: global.layout.footer
  })
};
</script>