<template>
  <main>
    <section class="container">
      <div class="row">
        <div class="col-12 text-danger text-center">
          <h1>{{ SerchGenre }}</h1>
        </div>
      </div>
      <div class="row pt-5" v-if="arrayCover.length !== 0">
        <div class="col-12 d-flex justify-content-center flex-wrap">
          <Figure
            v-for="(element, index) in newSerchGenre"
            :key="index"
            :poster="element.poster"
            :title="element.title"
            :author="element.author"
            :year="element.year"
          />
        </div>
      </div>
      <div class="row" v-else>
        <div class="col-12 text-center">
          <img
            src="http://media.tenor.com/images/b545eb51805026b335466195bb61f0a4/tenor.gif"
            alt="http://media.tenor.com/images/b545eb51805026b335466195bb61f0a4/tenor.gif"
            class="transparent momento"
          />
          <h1 class="text-white">Loading...</h1>
        </div>
      </div>
    </section>
  </main>
</template>

<script>
import axios from "axios";
import Figure from "../components/Main/Figure.vue";

export default {
  name: "HomeMain",
  props: ["SerchGenre"],
  components: {
    Figure,
  },
  data() {
    return {
      arrayCover: [],
      /*  current: 0, */
    };
  },
  created: function () {
    setTimeout(this.getApiArtist, 3500);
  },

  methods: {
    getApiArtist() {
      const self = this;
      axios
        .get("https://flynn.boolean.careers/exercises/api/array/music")
        .then((result) => {
          const resultLength = result.data.response.length;
          /* console.log("indice", current); */
          for (let i = 0; i < resultLength; i++) {
            console.log("indice", i);

            self.arrayCover.push(result.data.response[i]);
          }
          console.log("array", self.arrayCover);
        })
        .catch((error) => {
          console.log(error);
        });
    },
  },
  computed: {
    newSerchGenre() {
      console.log("funzione main", this.SerchGenre);
      return this.arrayCover.filter((element) =>
        element.genre.includes(this.SerchGenre)
      );
    },
  },
};
</script>

<style lang="scss" scoped>
@import "@/style/main-style.scss";
main {
  background-color: $brand_secondary;
  height: calc(100vh - 8vh);
  overflow: auto;
  figure {
    background-color: $color_primary;
    border-radius: 2.5%;
    height: 450px;
    img {
      width: 250px;
      height: 250px;
      border-radius: 5%;
    }
    h3 {
      color: white;
    }
    h4 {
      color: $brand_tertiary;
    }
  }
}
.momento {
  margin: 5rem 0;
  width: 520px;
  height: 439px;
}
</style>