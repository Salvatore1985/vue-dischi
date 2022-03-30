<template>
  <figure class="m-3 text-center">
    <a href="#">
      <img class="p-2" :src="poster" :alt="title" />
      <h3 class="p-3">{{ title }}</h3>
      <h4>{{ author }}</h4>
      <h4>{{ year }}</h4>
    </a>
  </figure>
</template>

<script>
export default {
  name: "FigureCards",
  props: ["poster", "title", "author", "genre", "year"],
};
</script>

<style lang="scss" scoped>
@import "@/style/main-style.scss";
figure {
  background-color: $color_primary;
  border-radius: 2.5%;
  width: $quote_cards;
  height: 550px;

  img {
    width: $quote_cards;
    height: $quote_cards;
    border-radius: 5%;
  }
  h3 {
    color: white;
  }
  h4 {
    color: gray;
  }
}
</style>