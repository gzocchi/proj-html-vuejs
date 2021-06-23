<template>
  <div class="container">
    
    <SectionTitle
      title="Featured Product"
      subtitle="Must have products from our top sellers"
    />

    <section class="products_btn">
      <button type="button" class="btn my_btn active">Men</button>
      <button type="button" class="btn my_btn">Women</button>
      <button type="button" class="btn my_btn">Accessories</button>
    </section>

    <section class="products_card">
      <ProductCard :product="products.men.leather_jacket" />
      <ProductCard :product="products.men.leather_suit" />
      <ProductCard :product="products.men.blue_jacket" />
      <ProductCard :product="products.men.black_leather_jacket" />
    </section>

  </div>
</template>

<script>
import SectionTitle from "./SectionTitle.vue";
import ProductCard from "./ProductCard.vue";

export default {
  name: "Featured",
  components: {
    SectionTitle,
    ProductCard,
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

.products_btn {
  display: flex;
  justify-content: center;

  .my_btn {
    padding: 10px 30px;
    background-color: rgba($fedora, 0.1);
    border-radius: 0;

    &.active,
    &:hover {
      background-color: $white;
    }
  }
}

.products_card {
  display: flex;
  justify-content: center;
  align-items: center;
  margin-top: 20px;
}
</style>
