<template>
  <header>
    <section class="nav_top container-fluid">
      <div class="container">
        <h2>nav top</h2>
      </div>
    </section>
    <section class="nav_bottom container-fluid">
      <div class="container">
        <nav class="my_nav navbar navbar-expand-lg navbar-light ">
          <div class="container-fluid">
            <a class="navbar-brand" href="#">
              <img
                src="../assets/img/logo/classic_shop_logo1x.png"
                alt="logo"
              />
            </a>
            <button
              class="navbar-toggler"
              type="button"
              data-bs-toggle="collapse"
              data-bs-target="#navbarSupportedContent"
              aria-controls="navbarSupportedContent"
              aria-expanded="false"
              aria-label="Toggle navigation"
            >
              <span class="navbar-toggler-icon"></span>
            </button>
            <div class="collapse navbar-collapse" id="navbarSupportedContent">
              <ul class="navbar-nav me-auto mb-2 mb-lg-0">
                <li
                  v-for="element in navLink"
                  :key="element"
                  :class="{ dropdown: element.drop }"
                  class="nav-item"
                >
                  <a
                    v-if="!element.drop"
                    class="nav-link"
                    :class="{ active: element.active }"
                    aria-current="page"
                    :href="element.link"
                    >{{ element.name }}</a
                  >
                  <a
                    v-else
                    class="nav-link dropdown-toggle"
                    :class="{ active: element.active }"
                    :href="element.link"
                    id="navbarDropdown"
                    role="button"
                    data-bs-toggle="dropdown"
                    aria-expanded="false"
                  >
                    {{ element.name }}
                  </a>
                  <ul
                    v-if="element.drop"
                    class="dropdown-menu"
                    aria-labelledby="navbarDropdown"
                  >
                    <li v-for="subelement in element.drop" :key="subelement">
                      <a class="dropdown-item" href="#">{{
                        subelement.name
                      }}</a>
                    </li>
                  </ul>
                </li>
              </ul>

              <button class="btn btn-primary px-4 text-uppercase" type="submit">
                Shop Now!
              </button>

              <i class="fas fa-search"></i>
            </div>
          </div>
        </nav>
      </div>
    </section>
  </header>
</template>

<script>
export default {
  name: "Header",
  props: ["social", "navLink"],
  data() {
    return {};
  },
};
</script>

<style scoped lang="scss">
@import "../assets/style/general";

.nav_top {
  height: 40px;
  border-bottom: 1px solid $fedora;
}

.nav_bottom {
  height: 70px;

  .my_nav {
    height: 100%;

    button {
      border-radius: 50px;
    }

    i {
      cursor: pointer;
    }
  }
}
</style>
