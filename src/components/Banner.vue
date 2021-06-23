<template>
  <section>
    <div>
      <i class="fas fa-clone"></i>
      <p class="m-0">Demos</p>
    </div>
    <div>
      <p class="m-0 price"><span>$</span>39</p>
      <p class="m-0">On Sale</p>
    </div>
  </section>
</template>

<script>
export default {
  name: "Banner",
};
</script>

<style scoped lang="scss">
@import "../assets/style/variables";

section {
  position: fixed;
  z-index: 2;
  right: 20px;
  top: 140px;

  div {
    display: flex;
    flex-direction: column;
    justify-content: space-around;
    align-items: center;
    height: 80px;
    width: 80px;
    padding: 3px;
    margin-bottom: 5px;
    background-color: $white;
    border-radius: 7px;
    cursor: pointer;
    box-shadow: 0px 0px 30px 3px rgba($fedora, 0.3);

    i,
    .price {
      font-size: 35px;
    }

    .price {
      color: #67df85;
    }
    span {
      font-size: 16px;
      vertical-align: text-top;
    }
  }
}
</style>
