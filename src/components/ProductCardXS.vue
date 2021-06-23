<template>
  <div class="prod_review py-2">
    <div class="info">
      <h4 class="my-1 me-2">{{ product.name }}</h4>

      <div class="star my-1" v-if="product.vote">
        <i v-for="n in product.vote" :key="n" class="fas fa-star"></i>
      </div>

      <span :class="{ discount: product.discountedPrice }" class="me-2">
        &dollar;{{ product.originalPrice }}</span
      >
      <span v-if="product.discountedPrice" :class="{ discounted: product.discountedPrice }">
        &dollar;{{ product.discountedPrice }}
      </span>
    </div>

    <div class="image">
      <img :src="product.img" :alt="product.name" />
    </div>
  </div>
</template>

<script>
export default {
  name: "ProductCardXS",
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

.prod_review {
  display: flex;
  width: 100%;
  height: 100px;
  border-bottom: 1px solid rgba($fedora, 0.3);

  .info {
    flex-grow: 1;
    h4 {
      display: inline-block;
      font-size: 14px;
      cursor: pointer;
    }

    i {
      color: $havelock_blue;
    }

    span {
      font-size: 18px;

      &.discounted {
        text-decoration: underline;
      }

      &.discount {
        text-decoration: line-through;
      }
    }
  }

  .image {
    height: 100%;

    img {
      height: 100%;
      cursor: pointer;
    }
  }
}
</style>
