<template>
  <main>
    <section class="container">
      <div class="row pt-5">
        <div class="col-12 d-flex justify-content-center flex-wrap">
          <Figure
            v-for="(element, index) in arrayCover"
            :key="index"
            :poster="element.poster"
            :title="element.title"
            :author="element.genre"
            :year="element.year"
          />

          <!-- <figure class="m-3 text-center">
            <a href="">
              <img
                class="img-fluid p-2"
                :src="element.poster"
                :alt="element.title"
              />
              <h3 class="p-3">{{ element.title }}</h3>
              <h4>{{ element.author }}</h4>
              <h4>{{ element.year }}</h4>
            </a>
          </figure> -->
          <!--  <div class="text-white">{{ arrayCover[0].genre }}</div> -->
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
  components: {
    Figure,
  },
  data() {
    return {
      arrayCover: [],
    };
  },
  created: function () {
    this.getApiArtist();
  },

  methods: {
    getApiArtist() {
      axios
        .get("https://flynn.boolean.careers/exercises/api/array/music")
        .then((result) => {
          const current = result.data.response.length;
          console.log("indice", current);
          for (let i = 0; i < current; i++) {
            const coverlistPoster = result.data.response[i].poster;
            const coverlistTitle = result.data.response[i].title;
            const coverlistAuthor = result.data.response[i].author;
            const coverlistGenre = result.data.response[i].genre;
            const coverlistYear = result.data.response[i].year;
            this.addObjCover(
              coverlistPoster,
              coverlistTitle,
              coverlistAuthor,
              coverlistGenre,
              coverlistYear
            );
          }
        })
        .catch((error) => {
          console.log(error);
        });
    },
    /**
     *
     * Funzione di ottimizzazione per creare un oggeto
     */
    addObjCover(poster, title, author, genre, year) {
      const newArrayCover = {
        poster: poster,
        title: title,
        author: author,
        genre: genre,
        year: year,
      };

      this.arrayCover.push(newArrayCover);
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
      color: gray;
    }
  }
}
</style>