<template>
  <div class="prod_card_small">
    <div class="img_card">
      <img :src="product.img" :alt="product.name" />

      <div class="info">
        <h4 class="my-2">{{ product.name }}</h4>
        <p class="my-2">{{ productTag }}</p>
        <span :class="{ discount: product.discountedPrice }">
          &dollar;{{ product.originalPrice }}</span
        >
        <span v-if="product.discountedPrice">
          &dollar;{{ product.discountedPrice }}
        </span>
      </div>
      <div class="details">
        <a href="#"><i class="fas fa-shopping-cart"></i> Add to cart</a>
        <a href="#"><i class="fas fa-list-ul"></i> Details</a>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "ProductCardSmall",
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

.prod_card_small {
  color: $white;

  .img_card {
    position: relative;

    img {
      width: 100%;
    }

    .info {
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      text-align: center;
      opacity: 0;
    }

    .details {
      position: absolute;
      bottom: 30px;
      left: 10%;
      width: 80%;
      display: flex;
      justify-content: space-between;
      opacity: 0;

      a {
        text-decoration: none;
        color: inherit;
        font-weight: 700;
        cursor: pointer;
      }
    }

    &:hover {
      background: $card_gradient;
      & > img {
        opacity: 0.1;
      }
      & > .info {
        opacity: 1;
      }
      & > .details {
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

    &:not(.discount) {
      font-weight: 700;
    }

    &.discount {
      text-decoration: line-through;
      font-size: 12px;
    }
  }
}
</style>
