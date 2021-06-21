<template>
  <header>
    <section class="nav_top container-fluid">
      <div class="container">
        <div class="row">
          <div class="social col-6 p-1">
            <a v-for="item in social" :key="item" :href="item.link">
              <i :class="[item.icon]"></i>
            </a>
          </div>
          <div class="user_section col-6">
            <a href="#">Shopping Cart</a>
            <a href="#">My Account <i class="fas fa-chevron-down"></i></a>
            <a href="#" class="active"
              ><i class="fas fa-shopping-cart"></i> Cart
              <i class="fas fa-chevron-down"></i
            ></a>
          </div>
        </div>
      </div>
    </section>
    <section class="nav_bottom container-fluid">
      <div class="container">
        <nav class="my_nav navbar navbar-expand-lg navbar-light p-0">
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

              <button class="btn px-4 text-uppercase" type="submit">
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

header {
  height: $header_h;
  color: $fedora;

  .nav_top {
    height: $nav-top_h;
    border-bottom: 0.5px solid rgba($fedora, 0.5);

    & > div {
      height: 100%;
    }

    .social,
    .user_section {
      display: flex;
      align-items: center;
      height: 100%;
    }
    .social {
      a {
        color: inherit;
        i {
          margin: 10px;
        }
      }
    }
    .user_section {
      justify-content: flex-end;
      line-height: $nav-top_h;

      a {
        height: 100%;
        padding: 0 20px;
        color: inherit;
        text-decoration: none;

        &:hover,
        &.active {
          background-color: rgba($fedora, 0.1);
        }

        &:nth-child(2) {
          border-left: 0.5px solid rgba($fedora, 0.5);
          border-right: 0.5px solid rgba($fedora, 0.5);
        }

        &:last-child {
          width: 200px;
          text-align: center;
        }

        i {
          margin: 5px;
        }
      }
    }
  }

  .nav_bottom {
    // height: $nav-top_h;

    .my_nav {
      height: $nav-bottom_h;
      background-color: $white;

      & > div {
        height: 100%;
      }

      #navbarSupportedContent {
        height: 100%;
      }

      button {
        border-radius: 50px;
        color: $white;
        background-color: $havelock_blue;
        border-color: $havelock_blue;
        font-weight: 500;
      }

      i {
        cursor: pointer;
      }
    }
    .navbar-light .navbar-nav .show > .nav-link[data-v-61dd7a3d],
    .navbar-light .navbar-nav .nav-link.active[data-v-61dd7a3d] {
      color: $havelock_blue;
    }
    // .active::after {
    //   content: "";
    //   position: absolute;
    //   top: - 100%;
    //   left: 0;
    //   transform: translateY(+100%);
    //   display: block;
    //   height: 1px;
    //   width: 100%;
    //   margin: 0;
    //   background-color: $havelock_blue;
    // }
  }
}
</style>
