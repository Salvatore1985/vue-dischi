<template>
  <main>
    <!-- <MainCards/> -->
    <section class="container">
      <div class="row pt-5">
        <div class="col-12 d-flex">
          <figure class="m-3 text-center">
            <a href="">
              <img
                class="img-fluid p-2"
                src="https://www.onstageweb.com/wp-content/uploads/2018/09/bon-jovi-new-jersey.jpg"
                alt="..."
              />
              <h3 class="p-3">album</h3>
              <h4>nome artista</h4>
              <h4>anno</h4>
            </a>
          </figure>
          <figure class="m-3 text-center">
            <a href="">
              <img
                class="img-fluid p-2"
                src="https://www.onstageweb.com/wp-content/uploads/2018/09/bon-jovi-new-jersey.jpg"
                alt="..."
              />
              <h3 class="p-3">album</h3>
              <h4>nome artista</h4>
              <h4 clas>anno</h4>
            </a>
          </figure>
          <figure class="m-3 text-center">
            <a href="">
              <img
                class="img-fluid p-2"
                src="https://www.onstageweb.com/wp-content/uploads/2018/09/bon-jovi-new-jersey.jpg"
                alt="..."
              />
              <h3 class="p-3">album</h3>
              <h4>nome artista</h4>
              <h4>anno</h4>
            </a>
          </figure>
        </div>
      </div>
    </section>
  </main>
</template>

<script>
export default {
  name: "HomeMain",
};
</script>

<style lang="scss" scoped>
@import "@/style/main-style.scss";
main {
  background-color: $brand_secondary;
  height: calc(100vh - 8vh);
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