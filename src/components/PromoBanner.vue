<template>
  <div class="container">
    <div class="promo off">
      <h3>70% Off</h3>
      <p>Vivamus tempor leo lacus, feugiat <br />ut magna aliquam erat.</p>
      <a href="#">View More</a>
    </div>
    <div class="promo shipping">
      <h3>Free Shipping</h3>
      <p>Vivamus tempor leo lacus, feugiat <br />ut magna aliquam erat.</p>
      <a href="#">View More</a>
    </div>
  </div>
</template>

<script>
export default {
  name: "PromoBanner",
};
</script>

<style scoped lang="scss">
@import "../assets/style/variables.scss";

.container {
  display: flex;
  justify-content: space-between;
  height: 100%;
  color: $white;

  .promo {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: flex-start;
    width: 49%;
    padding: 0 60px;

    h3 {
      margin: 0;
    }
    p {
      margin: 10px 0;
    }

    a {
      padding: 5px 15px;
      color: inherit;
      text-decoration: none;
      font-size: 12px;
      font-weight: 500;
      background-color: rgba($white, 0.2);
      border: 1px solid $white;
      border-radius: 25px;
    }
  }
  .off {
    background-image: url("../assets/img/products/promo_box_1_bg.jpg");
  }
  .shipping {
    background-image: url("../assets/img/products/promo_box_2_bg.jpg");
  }
  .off,
  .shipping {
    background-position: center;
    background-size: cover;
  }
}
</style>
