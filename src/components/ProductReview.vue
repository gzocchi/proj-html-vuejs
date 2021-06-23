<template>
  <div class="container">
    <div class="row">
      <div class="col-3">
        <h3 class="mb-3 text-uppercase">Featured</h3>
        <ProductCardReview :product="products.women.black_jacket" />
        <ProductCardReview :product="products.men.leather_jacket" />
        <ProductCardReview :product="products.women.hipster_black" />
      </div>
      <div class="col-3">
        <h3 class="mb-3 text-uppercase">On Sale</h3>
        <ProductCardReview :product="products.men.leather_jacket" />
        <ProductCardReview :product="products.men.leather_blue" />
        <ProductCardReview :product="products.accessories.modern_boots" />
      </div>
      <div class="col-3">
        <h3 class="mb-3 text-uppercase">Top Rated</h3>
        <ProductCardReview :product="products.accessories.leather_gloves" />
        <ProductCardReview :product="products.men.leather_jacket" />
        <ProductCardReview :product="products.women.spring_printed" />
      </div>
      <div class="col-3">
        <h3 class="mb-3 text-uppercase">Lastest reviews</h3>
      </div>
    </div>
  </div>
</template>

<script>
import ProductCardReview from "./ProductCardReview.vue";

export default {
  name: "ProductReview",
  components: {
    ProductCardReview,
  },
  props: {
    products: {
      type: Object,
      require: true,
    },
  },
};
</script>

<style scoped lang="scss">
@import "../assets/style/variables.scss";
h3 {
  font-size: 18px;
}
</style>
