<template>
  <nav class="">
    <div class="container-fluid px-5">
      <a class="navbar-brand" href="#">
        <img
          src="@/assets/img/Spotify_App_Logo.svg.png"
          alt=""
          width="50"
          height="50"
        />
      </a>
    </div>
  </nav>
</template>

<script>
export default {
  name: "HomeHeader",
};
</script>

<style lang="scss" scoped>
@import "@/style/main-style.scss";

nav {
  background-color: $color_primary;
  height: 8vh;
  a {
    line-height: 8vh;
  }
}
</style>