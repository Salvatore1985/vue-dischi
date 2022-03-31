<template>
  <section>
    <label class="px-2" for="genre">Filtra per autore</label>
    <select name="genre" id="genre">
      <option value="roch">Bon Jovi</option>
      <!--    <option value="pop">Queen</option>
      <option value="jazz">Sting</option>
      <option value="metal">Steve Gadd Band</option>
      <option value="metal">Iron Maiden</option>
      <option value="metal">Eric Clapton</option>
      <option value="metal">Deep Purple</option>
      <option value="metal">Metallica</option>
      <option value="metal">Dave Weckl</option>
      <option value="metal">Michael Jacjson</option> -->
    </select>
  </section>
</template>

<script>
export default {
  name: "HeardAuthor",
  /*  props: ["author"], */
};
</script>

<style lang="scss" scoped>
@import "@/style/main-style.scss";
label {
  color: $brand_tertiary;
}
</style>