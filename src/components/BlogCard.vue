<template>
  <div>
    <img :src="post.img" :alt="post.title" />

    <h4 class="mt-3">{{ post.title }}</h4>
    <span> {{ post.date }} | {{ post.comments.length }} Comments </span>

    <p class="mt-3">{{ post.text }}</p>
  </div>
</template>

<script>
export default {
  name: "BlogCard",
  props: {
    post: {
      type: Object,
      require: true,
    },
  },
};
</script>

<style scoped lang="scss">
@import "../assets/style/variables.scss";

div {
  cursor: pointer;

  img {
    width: 100%;
  }

  h4 {
    font-size: 18px;
    font-weight: 700;
  }
}
</style>
