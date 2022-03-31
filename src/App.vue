<template>
  <div id="app">
    <Header @serchGenre="newSerchGenre" />
    <Main :SerchGenre="SerchGenre" />
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Main from "./components/Main.vue";

export default {
  name: "App",
  components: {
    Header,
    Main,
  },
  data() {
    return {
      SerchGenre: "",
    };
  },
  methods: {
    newSerchGenre(strngToSerch) {
      console.log("genere selezionato", strngToSerch);
      this.SerchGenre = strngToSerch;
      console.log("data serch", this.SerchGenre);
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
