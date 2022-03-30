<template>
  <div id="app">
    <Header />
    <Main />
  </div>
</template>

<script>
import axios from "axios";

import Header from "./components/Header.vue";
import Main from "./components/Main.vue";

export default {
  name: "App",
  components: {
    Header,
    Main,
  },

  created: function () {
    this.getApiArtist();
  },

  methods: {
    getApiArtist() {
      axios
        .get("https://flynn.boolean.careers/exercises/api/array/music")
        .then((result) => {
          console.log(result);
        })
        .catch((error) => {
          console.log(error);
        });
    },
  },
};
</script>

<style lang="scss">
@import "@/style/main-style.scss";
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
</style>
