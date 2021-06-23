<template>
  <div id="app">
    <Header :social="socialInfo" :navLink="headerLink" />
    <Jumbotron title="Brand New Arrivals" msg="New collection from New York" />
    <Main :products="products" :collection="productCollection" />
    <Footer :social="socialInfo" :brand="brandInfo" :post="post" :tags="tag" />
    <Banner />
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Jumbotron from "./components/Jumbotron.vue";
import Main from "./components/Main.vue";
import Footer from "./components/Footer.vue";
import Banner from "./components/Banner.vue";

export default {
  name: "App",
  components: {
    Header,
    Jumbotron,
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
          icon: "fab fa-facebook-f",
        },
        instagram: {
          name: "Instagram",
          link: "#instagram_link",
          icon: "fab fa-instagram",
        },
        twitter: {
          name: "Twitter",
          link: "#twitter_link",
          icon: "fab fa-twitter",
        },
        youtube: {
          name: "YouTube",
          link: "#youtube_link",
          icon: "fab fa-youtube",
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
      products: {
        men: {
          leather_jacket: {
            name: "Black Leather Jacket",
            img: require("./assets/img/products/black_elegant_leather_jacket.jpg"),
            originalPrice: 235,
            discountedPrice: 200,
            tag: ["Jackets", "Jeans", "Men"],
            vote: 5,
          },
          leather_suit: {
            name: "Black Leather Suit",
            img: require("./assets/img/products/black_leather_suit.jpg"),
            originalPrice: 176,
            discountedPrice: false,
            tag: ["Jackets", "Men"],
            vote: false,
          },
          blue_jacket: {
            name: "Blue Jacket & Stripe Tee",
            img: require("./assets/img/products/blue_jacket_and_white_stripe_tee.jpg"),
            originalPrice: 580,
            discountedPrice: false,
            tag: ["Jackets", "Suits", "Men"],
            vote: false,
          },

          black_leather_jacket: {
            name: "Modern Black Leather Suit",
            img: require("./assets/img/products/modern_black_leather_suit.jpg"),
            originalPrice: 96,
            discountedPrice: false,
            tag: ["Jackets", "Men"],
            vote: false,
          },
          leather_blue: {
            name: "Blue Leather Jacket",
            img: require("./assets/img/products/blue_leather_jacket.jpg"),
            originalPrice: 80,
            discountedPrice: 60,
            tag: ["Jackets", "Men"],
            vote: false,
          },
        },
        women: {
          spring_printed: {
            name: "Spring Printed Dress",
            img: require("./assets/img/products/spring_printed_dress.jpg"),
            originalPrice: 47,
            discountedPrice: false,
            tag: ["Dress", "Women"],
            vote: 5,
          },
          modern_love: {
            name: "Modern Love Tee",
            img: require("./assets/img/products/modern_love_tee.jpg"),
            originalPrice: 68,
            discountedPrice: false,
            tag: ["T-Shirts", "Women"],
            vote: false,
          },
          black_jacket: {
            name: "Black Jacket",
            img: require("./assets/img/products/black_leather_jacket.jpg"),
            originalPrice: 125,
            discountedPrice: false,
            tag: ["Jacket", "Women"],
            vote: false,
          },
          hipster_black: {
            name: "Hipster Black Top",
            img: require("./assets/img/products/hipster_black_top.jpg"),
            originalPrice: 57,
            discountedPrice: false,
            tag: ["T-Shirts", "Women"],
            vote: false,
          },
        },
        accessories: {
          leather_gloves: {
            name: "Leather Gloves",
            img: require("./assets/img/products/leather_gloves.jpg"),
            originalPrice: 45,
            discountedPrice: false,
            tag: ["Accessories", "Gloves", "Men", "Women"],
            vote: 5,
          },
          casual_belts: {
            name: "Casual Leather Belts",
            img: require("./assets/img/products/casual_leather_belts.jpg"),
            originalPrice: 65,
            discountedPrice: false,
            tag: ["Accessories", "Men"],
            vote: false,
          },
          modern_boots: {
            name: "Modern Leather Boots",
            img: require("./assets/img/products/modern_leather_boots.jpg"),
            originalPrice: 50,
            discountedPrice: 30,
            tag: ["Accessories", "Men", "Miscellaneous", "Shoes"],
            vote: false,
          },
          brown_shoes: {
            name: "Brown Dress Shoes",
            img: require("./assets/img/products/brown_dress_shoes.jpg"),
            originalPrice: 46,
            discountedPrice: 36,
            tag: ["Accessories", "Miscellaneous", "Shoes", "Women"],
            vote: false,
          },
        },
      },
      productCollection: {
        winter: {
          name: "Winter Collection",
          msg: "Stylish and warm",
          link: "#_winter_collection",
          img: require("./assets/img/products/winter_collection_bg.jpg"),
        },
        spring: {
          name: "Spring Collection",
          msg: "Bright and colorful",
          link: "#_spring_collection",
          img: require("./assets/img/products/spring_collection_bg.jpg"),
        },
        autumn: {
          name: "Autumn Collection",
          msg: "Rich and Comfortable",
          link: "#_autumn_collection",
          img: require("./assets/img/products/autumn_collection_bg.jpg"),
        },
      },
      post: [
        {
          title: "Aenean lobortis sapien enim viverra",
          img: "./assets/img/blog/post_img_12-700x441.jpg",
          date: "September 9th, 2015",
          text:
            "Donec finibus sit amet orci eget ultricies. Praesent posuere ante ut erat fringilla,",
          comments: [],
        },
        {
          title: "Duis ac massa semper maximus",
          img: "./assets/img/blog/post_img_11-700x441.jpg",
          date: "September 9th, 2015",
          text:
            "Donec finibus sit amet orci eget ultricies. Praesent posuere ante ut erat fringilla,",
          comments: [],
        },
        {
          title: "Nunc fermint nulla eu justo sem id",
          img: "./assets/img/blog/post_img_10-700x441.jpg",
          date: "September 9th, 2015",
          text:
            "Donec finibus sit amet orci eget ultricies. Praesent posuere ante ut erat fringilla,",
          comments: [],
        },
        {
          title: "Aliquam posuere magna eget nibh",
          date: "September 9th, 2015",
          text:
            "Donec finibus sit amet orci eget ultricies. Praesent posuere ante ut erat fringilla,",
          comments: [],
        },
        {
          title: "Aliquam posuere magna eget nibh",
          date: "September 8th, 2015",
          text:
            "Donec finibus sit amet orci eget ultricies. Praesent posuere ante ut erat fringilla,",
          comments: [],
        },
        {
          title: "Cras ac nulla ac consecte rutrum",
          date: "September 8th, 2015",
          text:
            "Donec finibus sit amet orci eget ultricies. Praesent posuere ante ut erat fringilla,",
          comments: [],
        },
        {
          title: "Fusce mattis nunc ut aliquam",
          date: "September 8th, 2015",
          text:
            "Donec finibus sit amet orci eget ultricies. Praesent posuere ante ut erat fringilla,",
          comments: [],
        },
      ],
      tag: [
        "Black",
        "boots",
        "Brown",
        "Casual",
        "D&G",
        "Fabric",
        "flowers",
        "Grey",
        "hat",
        "Hipster",
        "lines",
        "multi-purpose",
        "New York",
        "Outdoors",
        "red",
        "responsive",
        "summer",
        "sweater",
        "Travel",
        "warm",
        "White",
        "winter",
      ],
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
