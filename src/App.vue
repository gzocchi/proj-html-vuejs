<template>
  <div id="app">
    <Header :social="socialInfo" :navLink="headerLink" />
    <Main />
    <Footer :social="socialInfo" :brand="brandInfo" />
    <Banner />
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Main from "./components/Main.vue";
import Footer from "./components/Footer.vue";
import Banner from "./components/Banner.vue";

export default {
  name: "App",
  components: {
    Header,
    Main,
    Footer,
    Banner,
  },
  data() {
    return {
      brandInfo: {
        name: "Avada",
        city: "New York, NY 555555",
        street: "12345 North Main Street",
        phone: "1.800.555.6789",
        email: "info@company.com",
        website: "www.theme-fusion.com",
      },
      socialInfo: {
        facebook: {
          name: "Facebook",
          link: "#facebook_link",
          icon: "fab fa-facebook-f"
        },
        instagram: {
          name: "Instagram",
          link: "#instagram_link",
          icon: "fab fa-instagram"
        },
        twitter: {
          name: "Twitter",
          link: "#twitter_link",
          icon: "fab fa-twitter"
        },
        youtube: {
          name: "YouTube",
          link: "#youtube_link",
          icon: "fab fa-youtube"
        },
      },
      headerLink: {
        home: {
          name: "Home",
          link: "#",
          active: true,
          drop: {
            action1: {
              name: "Action",
              link: "#",
            },
            action2: {
              name: "Another action",
              link: "#",
            },
            action3: {
              name: "Something else here",
              link: "#",
            },
          },
        },
        shop: {
          name: "Shop",
          link: "#",
          active: false,
          drop: {
            action1: {
              name: "Action",
              link: "#",
            },
          },
        },
        prod: {
          name: "Products",
          link: "#",
          active: false,
          drop: {
            action1: {
              name: "Action",
              link: "#",
            },
            action2: {
              name: "Another action",
              link: "#",
            },
            action3: {
              name: "Something else here",
              link: "#",
            },
          },
        },
        cat: {
          name: "Categories",
          link: "#",
          active: false,
          drop: {
            action1: {
              name: "Action",
              link: "#",
            },
            action2: {
              name: "Another action",
              link: "#",
            },
            action3: {
              name: "Something else here 1",
              link: "#",
            },
            action4: {
              name: "Something else here 2",
              link: "#",
            },
            action5: {
              name: "Something else here 3",
              link: "#",
            },
          },
        },
        news: {
          name: "News",
          link: "#",
          active: false,
        },
        el: {
          name: "Elements",
          link: "#",
          active: false,
          drop: {
            action1: {
              name: "Action",
              link: "#",
            },
            action2: {
              name: "Another action",
              link: "#",
            },
          },
        },
      },
    };
  },
};
</script>

<style lang="scss">
@import "./assets/style/general.scss";

#app {
  font-family: $font_family;
  font-size: $font_size;
  color: $shark;
}
</style>
