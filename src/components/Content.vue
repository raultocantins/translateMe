<template>
  <v-main class="main">
    <v-toolbar light class="toolbar" fluid>
      <v-select
        :items="items"
        :label="items[0]"
        solo
        class="mr-4 mt-5 select"
        v-model="de"
      />
      <v-select
        :items="items"
        :label="items[1]"
        solo
        v-model="to"
        class="mt-5"
      />
    </v-toolbar>

    <v-col cols="12" class="content">
      <v-col md="6">
        <v-textarea
          class="textarea"
          clearable
          outlined
          name="input-7-4"
          label="Digite o Texto"
          :value="input"
          v-model="input"
          @input="translateText"
        ></v-textarea>
      </v-col>
      <v-col md="6">
        <v-textarea
          class="textarea"
          outlined
          name="input-7-4"
          label="Tradução"
          :value="output"
          v-model="output"
        ></v-textarea>
      </v-col>
    </v-col>
    <v-footer absolute class="font-weight-medium footer">
      <v-col class="text-center text-footer" cols="12">
        Developed by Alex raul
        <a href="https://www.github.com/raultocantins">
          <img :src="git" alt="github" style="margin-left: 10px" />
        </a>
      </v-col>
    </v-footer>
  </v-main>
</template>

<script>
import Axios from "axios";
import git from "../assets/github.svg";
export default {
  data: function () {
    return {
      items: [
        "en (Inglês)",
        "pt (Português)",
        "fr (Francês)",
        "zh (Chinês)",
        "es  (Espanhol)",
      ],
      input: "",
      output: "",
      de: "en",
      to: "pt",
      git: git,
    };
  },
  methods: {
    translateText() {
      var i = this.de.substring(0, 3).trim();
      var o = this.to.substring(0, 3).trim();
      Axios(
        `https://api.mymemory.translated.net/get?q=${this.input}!&langpair=${i}|${o}`
      )
        .then((res) => {
          this.output = res.data.responseData.translatedText;
        })
        .catch((e) => {
          alert(e);
        });
    },
  },
  components: {},
};
</script>

<style scoped>
.content {
  display: flex;
  justify-content: center;
  align-items: center;
}
.text-footer {
  display: flex;
  align-items: center;
  justify-content: center;
}
.toolbar {
  background-color: transparent;
  box-shadow: none !important;

  padding: 50px;
}
</style>