<template>
  <main>
    <section class="products">
      <h2>Featured Product</h2>
      <div class="collection container-fluid">
        <div class="row">
          <div
            v-for="(season, index) in collection"
            :key="index"
            class="col-4 p-0"
          >
            <Collection :item="season" />
          </div>
        </div>
      </div>
      <h2>Best Seller</h2>
      <h2>Banner</h2>
      <h2>New Arrivals</h2>
    </section>

    <section class="blog">
      <h2>Blog Carousel</h2>
      <h2>Blog Extract</h2>
      <h2>Product Review</h2>
      <h2>Brand Logo</h2>
    </section>
    <h2></h2>
  </main>
</template>

<script>
import Collection from "./Collection.vue";

export default {
  name: "Main",
  components: {
    Collection,
  },
  props: ["collection"],
};
</script>

<style scoped lang="scss">
@import "../assets/style/variables.scss";

.collection .col-4 {
  height: $collection_card_h;
}
</style>
