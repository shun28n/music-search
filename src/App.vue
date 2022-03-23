<template>
  <v-app>
    <v-app-bar app color="primary" dark>
      <v-toolbar-title class="headline text-uppercase">
        <router-link to="/" style="color: white; text-decoration: none">
          <span>MUSIC SEARCH</span>
        </router-link>
      </v-toolbar-title>

      <v-spacer></v-spacer>

      <v-btn text to="/">
        <span class="mr-2">HOME</span>
        <v-icon>mdi-open-in-new</v-icon>
      </v-btn>
    </v-app-bar>

    <v-main>
      <router-view />
    </v-main>
  </v-app>
</template>

<script>
export default {
  name: "App",
};
</script>
