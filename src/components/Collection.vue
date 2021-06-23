<template>
  <div class="pb-5" :style="{ backgroundImage: `url(${item.img})` }">
    <h4 class="m-0 fw-bolder">{{ item.name }}</h4>
    <h6 class="my-3 text-uppercase">{{ item.msg }}</h6>
    <a :href="item.link" class="text-uppercase">View More</a>
  </div>
</template>

<script>
export default {
  name: "Collection",
  props: {
    item: {
      type: Object,
      require: true,
    },
  },
};
</script>

<style scoped lang="scss">
@import "../assets/style/variables.scss";

div {
  height: 100%;
  display: flex;
  flex-direction: column;
  justify-content: flex-end;
  align-items: center;
  color: $white;
  background-position: top;
  background-size: cover;

  h6 {
    font-size: 14px;
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
</style>
