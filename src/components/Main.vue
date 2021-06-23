<template>
  <main>
    <section class="products">
      <div v-if="products" class="featured container-fluid">
        <Featured :products="products" />
      </div>
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
      <div v-if="products" class="best_seller container-fluid">
        <BestSeller :products="products" />
      </div>
      <div v-if="collection" class="promo_banner container-fluid">
        <PromoBanner />
      </div>
      <div v-if="products" class="new_arrivals container-fluid">
        <NewArrivals :products="products" />
      </div>
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
import Featured from "./Featured.vue";
import Collection from "./Collection.vue";
import BestSeller from "./BestSeller.vue";
import PromoBanner from "./PromoBanner.vue";
import NewArrivals from "./NewArrivals.vue";

export default {
  name: "Main",
  components: {
    Featured,
    Collection,
    BestSeller,
    PromoBanner,
    NewArrivals,
  },
  props: {
    products: {
      type: Object,
      require: true,
    },
    collection: {
      type: Object,
      require: true,
    },
  },
};
</script>

<style scoped lang="scss">
@import "../assets/style/variables.scss";

.featured,
.best_seller,
.new_arrivals {
  padding: 60px 0;
}

.collection .col-4 {
  height: $collection_card_h;
}

.promo_banner {
  height: $promo_banner_h;
  padding: 90px 0;
  background-image: url("../assets/img/bkgd_confetti-compressor.jpg");
  background-position: center;
  background-size: auto;
  background-repeat: repeat;
}
</style>
