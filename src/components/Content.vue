<template>
  <v-content>
    <v-toolbar light class="mr-5 ml-5 pb-5"  src="https://cdn.vuetifyjs.com/images/backgrounds/vbanner.jpg">
      <v-select :items="items" :label="items[0]" solo class="mr-4 "/> 
      <v-select :items="items" :label="items[1]" solo></v-select>
    </v-toolbar>

    <v-col cols="12"  class="content">
      <v-col md="6" xs="12">
        <v-textarea
        
          outlined
          name="input-7-4"
          label="Outlined textarea"
          value="The Woodman set to work at once, and so sharp was his axe that the tree was soon chopped nearly through."
        ></v-textarea>
      </v-col>
      <v-col md="6" xs="12">
        <v-textarea
          outlined
          name="input-7-4"
          label="Outlined textarea"
          value="The Woodman set to work at once, and so sharp was his axe that the tree was soon chopped nearly through."
        ></v-textarea>
      </v-col>
    </v-col>
  </v-content>
</template>

<script>
export default {
  data: function () {
    return {
      items: ["PT", "EN"],
    };
  },
};
</script>

<style scoped>
.content{
    display: flex;
    justify-content: center;
    align-items: center;
}
</style>