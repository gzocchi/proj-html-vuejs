<template>
  <div class="container">
    <section class="title px-2">
      <hr />
      <h2 class="m-0">Featured Product</h2>
      <hr />
    </section>
    <h6 class="text-center py-2">Must have products from our top sellers</h6>
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
import ProductCard from "./ProductCard.vue";

export default {
  name: "Featured",
  components: {
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

.title {
  display: flex;
  justify-content: space-around;
  align-items: center;
  hr {
    display: inline-block;
    width: calc((100% - 350px) / 2);
    vertical-align: middle;
  }
  h2 {
    font-weight: 700;
    display: inline-block;
  }
}
h6 {
  color: $fedora;
  margin-bottom: 50px;
}

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
