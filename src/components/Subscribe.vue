<template>
  <div class="container py-5">
    <a href="#" class="mx-3">
      <i class="far fa-envelope"></i>
    </a>
    <h4 class="m-0 ps-3">Subscribe now and get special offers</h4>
    <input
      type="text"
      class="form-control"
      v-model.trim="email"
      @keydown.enter="sendMail"
      placeholder="insert your email"
    />
    <button
      class="btn my_btn px-4 mx-3 text-uppercase"
      @click="sendMail"
      type="button"
    >
      send
    </button>
  </div>
</template>

<script>
export default {
  name: "Subscribe",
  data() {
    return {
      email: "",
    };
  },
  methods: {
    sendMail() {
      this.email = "";
    },
  },
};
</script>

<style scoped lang="scss">
@import "../assets/style/variables";

div {
  display: flex;
  justify-content: space-around;
  align-items: center;

  a {
    display: flex;
    height: 50px;
    width: 50px;
    color: inherit;
    text-decoration: none;
    background-color: $shark;
    border-radius: 50%;
    i {
      margin: auto;
      font-size: 30px;
      color: $fedora;
    }
  }
  h4 {
    flex-grow: 1;
  }
  input {
    max-width: 350px;
    border-radius: 50px;
  }
  button.my_btn {
    border-radius: 50px;
    color: $white;
    background-color: $havelock_blue;
    border-color: $havelock_blue;
    font-weight: 500;
  }
}
</style>
