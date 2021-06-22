<template>
  <footer>
    <section class="subscribe container-fluid">
      <Subscribe />
    </section>
    <section class="info">
      <h2>info</h2>
    </section>
    <section class="copyright">
      <h2>copyright</h2>
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
  }
}
</style>
