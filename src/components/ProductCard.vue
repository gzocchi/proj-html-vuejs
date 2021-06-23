<template>
  <div class="prod_card">
    <div class="img_card">
      <img :src="product.img" :alt="product.name" />
    </div>

    <h4>{{ product.name }}</h4>
    <p>{{ productTag }}</p>
    <span :class="{ discount: product.discountedPrice }">
      &dollar;{{ product.originalPrice }}</span
    >
    <span v-if="product.discountedPrice">
      &dollar;{{ product.discountedPrice }}
    </span>
  </div>
</template>

<script>
export default {
  name: "ProductCard",
  props: {
    product: {
      type: Object,
      require: true,
    },
  },
  computed: {
    productTag() {
      return this.product.tag.join(", ");
    },
  },
};
</script>

<style scoped lang="scss">
@import "../assets/style/variables.scss";

.prod_card {
  height: 100%;
  padding: 20px;
  .img_card {
    img {
      width: 100%;
    }
  }
  span {
    font-size: 18px;
    color: $havelock_blue;

    &.discount {
      text-decoration: line-through;
      font-size: 12px;
    }
  }
}
</style>
