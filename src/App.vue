<template>
  <v-app>
    <v-app-bar
      src="https://cdn.vuetifyjs.com/images/backgrounds/vbanner.jpg"
      app
      color="primary"
      dark
      class="appbar"
    >
      <h1>TranslateMe</h1>
    </v-app-bar>
    <Content />
  </v-app>
</template>

<script>
import Content from "./components/Content";

export default {
  name: "App",

  components: {
    Content,
  },

  data: () => ({
    //
  }),
};
</script>
<style scoped>
.appbar {
  display: flex;
  justify-content: center;
}
</style>