<template>
  <footer>
    <section class="subscribe container-fluid">
      <Subscribe />
    </section>
    <section class="info container">
      <div class="row py-5">
        <div class="brand px-3 col-3">
          <img
            src="../assets/img/logo/classic_shop_logo_footer.png"
            alt="Logo"
            class="mb-2"
          />
          <ul class="m-0 p-0 py-4">
            <li v-if="brand.street">
              {{ brand.street }}
            </li>
            <li v-if="brand.city">
              {{ brand.city }}
            </li>
            <li v-if="brand.state">{{ brand.state }}</li>
            <li v-if="brand.phone">Phone: {{ brand.phone }}</li>
            <li v-if="brand.mobile">Mobile: {{ brand.mobile }}</li>
            <li v-if="brand.email">
              Email: <a :href="`mailto:${brand.email}`">{{ brand.email }}</a>
            </li>
            <li v-if="brand.website">
              Web: <a :href="brand.website" target="_blank">{{ web }}</a>
            </li>
          </ul>
          <div class="social mt-2">
            <a v-for="(item, index) in social" :key="index" :href="item.link">
              <i :class="[item.icon]"></i>
            </a>
          </div>
        </div>

        <div class="products px-3 col-3">
          <h6 class="text-uppercase">top rated products</h6>
          <ProductCardXS :product="products.accessories.leather_gloves" />
          <ProductCardXS :product="products.men.leather_jacket" />
          <ProductCardXS :product="products.women.spring_printed" />
        </div>

        <div class="posts px-3 col-3">
          <h6 class="text-uppercase">recent posts</h6>
          <ul class="m-0 p-0">
            <li v-for="(item, index) in posts" :key="index" class="py-2">
              <i class="fas fa-chevron-right"></i>
              <a href="#">{{ item.title }}</a>
            </li>
          </ul>
        </div>

        <div class="tags px-3 col-3">
          <h6 class="text-uppercase">tags</h6>
          <div>
            <a v-for="(tag, index) in tags" :key="index" :href="`#${tag}`">
              {{ tag }}
            </a>
          </div>
        </div>
      </div>
    </section>
    <section class="copyright container-fluid text-center py-2">
      <p>
        &copy; Copyright 2012-2020 | Avada Theme by Theme Fusion | All Rights
        Reserved | Powered by WordPress
      </p>
      <img src="../assets/img/payment_cards_footer.png" alt="payment cards" />
    </section>
  </footer>
</template>

<script>
import Subscribe from "./Subscribe.vue";
import ProductCardXS from "./ProductCardXS.vue";

export default {
  name: "Footer",
  components: {
    Subscribe,
    ProductCardXS,
  },
  props: {
    social: {
      type: Object,
      require: true,
    },
    brand: {
      type: Object,
      require: true,
    },
    posts: {
      type: Array,
      require: true,
    },
    tags: {
      type: Array,
      require: true,
    },
    products: {
      type: Object,
      require: true,
    },
  },
  computed: {
    web() {
      let website = this.brand.website.split(".");
      website.splice(0, 1);
      return website.join(".");
    },
  },
};
</script>

<style scoped lang="scss">
@import "../assets/style/variables.scss";

footer {
  font-weight: 500;
  color: $white;
  background-color: #2b2e32;

  .subscribe {
    background-color: #303337;
  }

  a {
    color: inherit;
    text-decoration: none;
  }

  .info {
    font-size: 11px;

    ul {
      list-style: none;
    }

    h6 {
      font-size: 12px;
    }

    .brand {
      img {
        height: 40px;
      }
      li {
        margin: 5px 0;
      }
      .social {
        a {
          margin-right: 10px;
        }
      }
    }

    // .products {
    // }

    .posts {
      li {
        border-bottom: 1px solid $fedora;
        i {
          margin-right: 5px;
        }
      }
    }

    .tags {
      div {
        display: flex;
        flex-wrap: wrap;

        a {
          margin-right: 3px;
          margin-bottom: 3px;
          padding: 3px 4px;
          border: 1px solid $fedora;
        }
      }
    }
  }
  .copyright {
    background-color: #1d1f22;

    p {
      margin-top: 15px;
      font-size: 10px;
      font-weight: 500;
    }

    img {
      height: 20px;
    }
  }
}
</style>
