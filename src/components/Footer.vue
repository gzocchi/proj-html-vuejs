<template>
  <footer>
    <section class="subscribe container-fluid">
      <Subscribe />
    </section>
    <section class="info">
      <h2>info</h2>
    </section>
    <section class="copyright text-center py-2">
      <p>
        &copy; Copyright 2012-2020 | Avada Theme by Theme Fusion | All Rights
        Reserved | Powered by WordPress
      </p>
      <img src="../assets/img/payment_cards_footer.png" alt="payment cards" />
    </section>
  </footer>
</template>

<script>
import Subscribe from "./Subscribe.vue";

export default {
  name: "Footer",
  components: {
    Subscribe,
  },
  props: ["social", "brand", "post", "tag"],
};
</script>

<style scoped lang="scss">
@import "../assets/style/variables";

footer {
  color: $white;
  background-color: #1d1f22;

  .subscribe {
    background-color: #303337;
  }
  .info {
    background-color: #2b2e32;
  }
  .copyright {
    background-color: #1d1f22;
    p {
      margin-top: 15px;
      font-size: 10px;
      font-weight: 500;
    }
    img {
      height: 20px;
    }
  }
}
</style>
