<template>
  <nav>
    <div class="container-fluid">
      <div class="row px-5">
        <div class="col-12 d-flex justify-content-between align-items-center">
          <a href="#">
            <img
              src="@/assets/img/Spotify_App_Logo.svg.png"
              alt=""
              width="50"
              height="50"
            />
          </a>
          <!--  <Genre /> -->
          <section>
            <label class="px-2" for="genre">Filtra per genere</label>
            <select name="genre" id="genre" v-model="serchSelectGenre">
              <option
                value="Rock"
                @click="$emit('serchGenre', serchSelectGenre)"
              >
                Rock
              </option>
              <option
                @click="$emit('serchGenre', serchSelectGenre)"
                value="Pop"
              >
                Pop
              </option>
              <option
                @click="$emit('serchGenre', serchSelectGenre)"
                value="Jazz"
              >
                Jazz
              </option>
              <option
                @click="$emit('serchGenre', serchSelectGenre)"
                value="Metal"
              >
                Metal
              </option>
            </select>
            <span class="px-3">{{ serchSelectGenre }}</span>
          </section>
          <Author />
        </div>
      </div>
    </div>
  </nav>
</template>

<script>
/* import Genre from "../components/Header/Genre.vue"; */
import Author from "../components/Header/Author.vue";
export default {
  name: "HomeHeader",
  components: {
    /*   Genre, */
    Author,
  },
  data() {
    return {
      serchSelectGenre: "",
    };
  },
};
</script>

<style lang="scss" scoped>
@import "@/style/main-style.scss";

nav {
  background-color: $color_primary;
  height: 8vh;
  .row {
    height: 8vh;
  }
}
label,
span {
  color: $brand_tertiary;
}
</style>