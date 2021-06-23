<template>
  <main>
    <section class="products">
      <div v-if="products" class="featured container-fluid">
        <Featured :products="products" />
      </div>
      <div class="collection container-fluid">
        <div class="row">
          <div
            v-for="(season, index) in collection"
            :key="index"
            class="col-4 p-0"
          >
            <Collection :item="season" />
          </div>
        </div>
      </div>
      <div v-if="products" class="best_seller container-fluid">
        <BestSeller :products="products" />
      </div>
      <div v-if="collection" class="promo_banner container-fluid">
        <PromoBanner />
      </div>
      <div v-if="products" class="new_arrivals container-fluid">
        <NewArrivals :products="products" />
      </div>
    </section>

    <section class="blog">
      <div class="blog_carousel container_fluid  text-center">
        <div class="container py-5">
          <img
            src="../assets/img/blog/man_testimonial.png"
            alt="Darío Pineda"
            class="my-4"
          />
          <p>
            Curabitur non tristique tortor. Vestibulum aliquet suscipit ipsum in
            volutpat. Donec vel lacinia sem, vitae semper nulla. In hac
            habitasse platea dictumst. Mauris consectetur est et nibh sadip
            hendrerit bibendum.
          </p>
          <h5>Darío Pineda, <span class="fw-light fs-6">Theme Fusion</span></h5>
          <i class="fas fa-circle"></i>
          <i class="far fa-circle"></i>
        </div>
      </div>

      <div v-if="posts" class="new_arrivals container-fluid">
        <BlogExtract :posts="posts" />
      </div>

      <h2>Product Review</h2>

      <div class="brand_logo container-fluid">
        <h5 class="text-uppercase text-center my-3">Brand Logos</h5>
        <div class="logo container">
          <img src="../assets/img/blog/b_logotype_6.png" alt="Authentic" />
          <img src="../assets/img/blog/b_logotype_7.png" alt="Yard" />
          <img src="../assets/img/blog/b_logotype_1.png" alt="Forest" />
          <img src="../assets/img/blog/b_logotype_2.png" alt="Bedge" />
          <img src="../assets/img/blog/b_logotype_3.png" alt="Beard" />
        </div>
      </div>
    </section>
  </main>
</template>

<script>
import Featured from "./Featured.vue";
import Collection from "./Collection.vue";
import BestSeller from "./BestSeller.vue";
import PromoBanner from "./PromoBanner.vue";
import NewArrivals from "./NewArrivals.vue";

import BlogExtract from "./BlogExtract.vue";

export default {
  name: "Main",
  components: {
    Featured,
    Collection,
    BestSeller,
    PromoBanner,
    NewArrivals,
    BlogExtract,
  },
  props: {
    products: {
      type: Object,
      require: true,
    },
    collection: {
      type: Object,
      require: true,
    },
    posts: {
      type: Array,
      require: true,
    },
  },
};
</script>

<style scoped lang="scss">
@import "../assets/style/variables.scss";

.featured,
.best_seller,
.new_arrivals {
  padding: 60px 0;
}

.collection .col-4 {
  height: $collection_card_h;
}

.promo_banner {
  height: $promo_banner_h;
  padding: 90px 0;
  background-image: url("../assets/img/bkgd_confetti-compressor.jpg");
  background-position: center;
  background-size: auto;
  background-repeat: repeat;
}

.blog_carousel {
  color: $white;
  background-image: url(../assets/img/blog/testimonials_home_1_bg.jpg);
  background-position: center;
  background-size: cover;
  background-repeat: no-repeat;
  p {
    max-width: 60%;
    margin: 24px auto;
  }
  i {
    margin: 20px 3px;
    cursor: pointer;
  }
}

.brand_logo {
  padding: 50px;
  background-color: rgba($fedora, 0.1);

  h5 {
    font-size: 16px;
  }

  .logo {
    display: flex;
    justify-content: space-around;
    align-items: center;
    cursor: pointer;
  }
}
</style>
