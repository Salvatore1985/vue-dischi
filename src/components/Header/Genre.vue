<template>
  <section>
    <label class="px-2" for="genre">Filtra per genere</label>
    <select name="genre" id="genre">
      <option value="roch">Rock</option>
      <option value="pop">Pop</option>
      <option value="jazz">Jazz</option>
      <option value="metal">Metal</option>
    </select>
  </section>
</template>

<script>
export default {
  name: "HeardGenre",
  /*  props: ["poster", "title", "author", "genre", "year"], */
};
</script>

<style lang="scss" scoped>
@import "@/style/main-style.scss";
label {
  color: $brand_tertiary;
}
</style>