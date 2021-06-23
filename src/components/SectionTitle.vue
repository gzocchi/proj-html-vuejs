<template>
  <section>
    <div class="title px-2">
      <hr />
      <h2 class="m-0">{{ title }}</h2>
      <hr />
    </div>
    <h6 class="text-center py-2">{{ subtitle }}</h6>
  </section>
</template>

<script>
export default {
  name: "SectionTitle",
  props: {
    title: {
      type: String,
      require: true,
    },
    subtitle: {
      type: String,
    },
  },
};
</script>

<style scoped lang="scss">
@import "../assets/style/variables.scss";

.title {
  display: flex;
  justify-content: space-around;
  align-items: center;

  hr {
    display: inline-block;
    width: calc((100% - 350px) / 2);
    vertical-align: middle;
  }

  h2 {
    font-weight: 700;
    display: inline-block;
  }
}

h6 {
  color: $fedora;
  margin-bottom: 50px;
}
</style>
