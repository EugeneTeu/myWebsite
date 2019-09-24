<template>
  <v-app >
    <v-app-bar
     color="primary"
     :hide-on-scroll="true" fixed app>
      <v-container >
        <v-row justify="space-around">
          <v-toolbar-title v-text="title" />
          <v-btn rounded text to="/">
            <v-icon>mdi-face</v-icon>
            <v-text v-if="$vuetify.breakpoint.smAndUp">About Me</v-text>
          </v-btn>
          <v-btn rounded text to="/portfolio">
            <v-icon>mdi-file-chart</v-icon>
            <v-text v-if="$vuetify.breakpoint.smAndUp">Portfolio</v-text>
          </v-btn>
      </v-row>
      </v-container>
    </v-app-bar>
    <v-content class="pa-0">
      <v-container class="mt-12 pt-12 pb-12 mb-12" >
        <nuxt />
      </v-container >
    </v-content>
    <v-footer mt-12 :fixed="fixed" :light="true" title padless app>
      <v-row justify-center rows="12">
        <v-col cols="12" class="text-center">
          <v-title>Eugene Teu Chu Wei&copy; 2019</v-title>
        </v-col>
      </v-row>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      clipped: false,
      drawer: false,
      fixed: false,
      items: [
        {
          icon: "mdi-apps",
          title: "Welcome",
          to: "/"
        },
      ],
      title: "Eugene Teu"
    };
  }
};
</script>
