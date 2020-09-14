<template>
  <v-app>
    <v-app-bar app color="dark mb-5" dark>
      <!-- <v-toolbar-title>Edutecno</v-toolbar-title> -->
      <v-spacer></v-spacer>
      <v-btn to="/" text>Home</v-btn>
      <v-btn to="/apod" text>Apod</v-btn>
      <v-btn to="/rover" text>rover</v-btn>
    </v-app-bar>

    <v-main>
      <router-view></router-view>
    </v-main>

    <v-card height="150">
    <v-footer
      absolute
      color="dark"
      class="font-weight-medium"
      dark
    >
      <v-col
        class="text-center"
        cols="12"
      >
        {{ new Date().getFullYear() }} — <strong>API - NASA</strong>
      </v-col>
    </v-footer>
  </v-card>
  </v-app>
</template>

<script>

export default {
  name: 'App',

  components: {
  },

  data: () => ({
    //
  }),
};
</script>
