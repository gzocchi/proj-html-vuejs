<template>
  <div class="jumbotron-fluid">
    <h1 class="display-4">{{ title }}</h1>
    <p class="lead text-uppercase">
      {{ msg }}
    </p>
    <div class="button">
      <a class="btn my_btn btn-lg text-uppercase me-3" href="#" role="button"
        >view all</a
      >
      <a class="btn my_btn btn-lg text-uppercase" href="#" role="button"
        >lookbook</a
      >
    </div>
  </div>
</template>

<script>
export default {
  name: "Jumbotron",
  props: {
    title: {
      type: String,
      require: true,
    },
    msg: {
      type: String,
      require: true,
    },
  },
};
</script>

<style scoped lang="scss">
@import "../assets/style/general";

div.jumbotron-fluid {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  height: $jumbotron_h;
  color: $white;
  background-image: url("../assets/img/home1_slide_three_bg_2.jpg");
  background-position: center;
  background-size: cover;
  background-repeat: no-repeat;

  h1.display-4 {
    font-weight: 700;
  }
  p.lead,
  .my_btn {
    font-weight: 500;
  }

  .my_btn {
    color: $white;
    background-color: rgba($white, 0.2);
    border-color: $white;
    border-radius: 40px;

    &:hover {
      color: $white;
      background-color: $shocking;
    }
  }
}
</style>
