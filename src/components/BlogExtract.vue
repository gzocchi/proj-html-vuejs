<template>
  <div class="container">
    <SectionTitle
      title="From Our Blog"
      subtitle="The lastest Classic Shop news"
    />
    <section class="blog_card">
      <BlogCard :post="posts[0]" />
      <BlogCard :post="posts[1]" />
      <BlogCard :post="posts[2]" />
    </section>
  </div>
</template>

<script>
import SectionTitle from "./SectionTitle.vue";
import BlogCard from "./BlogCard.vue";

export default {
  neme: "BlogExtract",
  components: {
    SectionTitle,
    BlogCard,
  },
  props: {
    posts: {
      type: Array,
      require: true,
    },
  },
};
</script>

<style scoped lang="scss">
@import "../assets/style/variables.scss";

.blog_card {
  display: flex;
  justify-content: space-between;
  align-items: flex-start;

  & > div {
    width: calc(90% / 3);
  }
}
</style>
