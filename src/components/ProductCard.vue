<template>
  <div class="prod_card">
    <div class="img_card">
      <img :src="product.img" :alt="product.name" />
      <i class="fas fa-2x fa-check"></i>
    </div>

    <h4 class="my-2">{{ product.name }}</h4>
    <p class="my-2">{{ productTag }}</p>
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
    position: relative;
    img {
      width: 100%;
    }
    i {
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      padding: 15px;
      color: $white;
      background-color: $shark;
      border-radius: 50%;
      opacity: 0;
    }
    &:hover {
      background: $card_gradient;
      cursor: pointer;
      & > img {
        opacity: 0.1;
      }
      & > i {
        opacity: 1;
      }
    }
  }
  h4 {
    font-size: 16px;
    font-weight: 700;
  }
  p {
    font-size: 12px;
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
