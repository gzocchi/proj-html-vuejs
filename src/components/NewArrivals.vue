<template>
  <div class="container-fluid">
    <div class="container">
      <SectionTitle
        title="New Arrivals"
        subtitle="Brand new products from top designers"
      />
    </div>

    <section class="carousel_card">
      <i class="fas fa-chevron-left"></i>
      <ProductCardSmall :product="products.men.leather_jacket" />
      <ProductCardSmall :product="products.women.hipster_black" />
      <ProductCardSmall :product="products.men.leather_suit" />
      <ProductCardSmall :product="products.women.spring_printed" />
      <ProductCardSmall :product="products.women.modern_love" />
      <i class="fas fa-chevron-right"></i>
    </section>
  </div>
</template>

<script>
import SectionTitle from "./SectionTitle.vue";
import ProductCardSmall from "./ProductCardSmall.vue";

export default {
  name: "NewArrivals",
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
