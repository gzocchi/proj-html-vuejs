<template>
  <div class="container">
    <SectionTitle
      title="Best Seller"
      subtitle="Must have products from our top sellers"
    />

    <section class="carousel_card">
      <i class="fas fa-chevron-left"></i>
      <ProductCardSmall :product="products.women.spring_printed" />
      <ProductCardSmall :product="products.women.modern_love" />
      <ProductCardSmall :product="products.women.black_jacket" />
      <ProductCardSmall :product="products.men.leather_jacket" />
      <ProductCardSmall :product="products.women.hipster_black" />
      <i class="fas fa-chevron-right"></i>
    </section>
  </div>
</template>

<script>
import SectionTitle from "./SectionTitle.vue";
import ProductCardSmall from "./ProductCardSmall.vue";

export default {
  name: "BestSeller",
  components: {
    SectionTitle,
    ProductCardSmall,
  },
  props: {
    products: {
      type: Object,
      require: true,
    },
  },
  data() {
    return {};
  },
};
</script>

<style scoped lang="scss">
@import "../assets/style/variables.scss";

.carousel_card {
  display: flex;
  justify-content: center;
  align-items: center;
  position: relative;
  margin-top: 20px;

  & > div {
    width: calc(100% / 5);
  }

  i {
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
    padding: 25px 15px;
    background-color: rgba($fedora, 0.5);
    color: $white;
    cursor: pointer;
    z-index: 1;

    &.fa-chevron-left {
      left: 0;
    }
    &.fa-chevron-right {
      right: 0;
    }
  }
}
</style>
