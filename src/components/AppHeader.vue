<script>
import Menu from "./HeaderSections/Menu.vue";
export default {
  data() {
    return {
      headerImg: [
        {
          logoImg: "/teach/img/h1-rev-img-01.jpg",
          info: "We are Everlead",
          description:
            "Lorem ipsum, dolor sit amet consectetur adipisicing elit. Illo, odio illum. Ut delectus voluptas, tempora modi atque harum cumque deserunt?",
        },
        {
          logoImg: "/teach/img/rev-slider-main-home-img-02.png",
          info: "Help you achieve anything",
        },
        {
          logoImg: "/teach/img/rev-slider-main-home-img-03.jpg",
          info: "Our Team",
          description:
            "Lorem ipsum, dolor sit amet consectetur adipisicing elit. Illo, odio illum. Ut delectus voluptas, tempora modi atque harum cumque deserunt?",
        },
      ],
      menuItems: [
        {
          label: "homes",
          link: "/home",
          active: true,
          showDropdown: false,
          submenu: [
            { label: "Main Home", link: "/about-us" },
            { label: "Business Coaching", link: "/pricing" },
            { label: "Blog Divided", link: "/contact" },
            { label: "Grid Home", link: "/about-us" },
            { label: "Coaching Events", link: "/pricing" },
            { label: "Wellness Coaching", link: "/contact" },
            { label: "Landing", link: "/contact" },
          ],
        },
        {
          label: "pages",
          link: "/pages",
          showDropdown: false,
          submenu: [
            { label: "About us", link: "/about-us" },
            { label: "Pricing plans", link: "/pricing" },
            { label: "Contact us", link: "/contact" },
            { label: "Standard List", link: "/about-us" },
            { label: "Masonry", link: "/pricing" },
            { label: "Post Type", link: "/contact" },
          ],
        },
        {
          label: "blog",
          link: "/blog",
          showDropdown: false,
          submenu: [
            { label: "Standard List", link: "/about-us" },
            { label: "Masonry", link: "/pricing" },
            { label: "Post Type", link: "/contact" },
          ],
        },
        {
          label: "shop",
          link: "/shop",
          showDropdown: false,
          submenu: [
            { label: "Product List", link: "/about-us" },
            { label: "Product Single", link: "/pricing" },
            { label: "Shop Layouts", link: "/contact" },
          ],
        },
        {
          label: "events",
          link: "/events",
          showDropdown: false,
          submenu: [
            { label: "Event List", link: "/about-us" },
            { label: "Event Day", link: "/pricing" },
            { label: "Event Calendar", link: "/contact" },
            { label: "Single Event", link: "/about-us" },
            { label: "Party", link: "/pricing" },
            { label: "Shop Layouts", link: "/contact" },
          ],
        },
        {
          label: "elements",
          link: "/elements",
          showDropdown: false,
          submenu: [
            { label: "Headings", link: "/headings" },
            { label: "Columns", link: "/columns" },
            { label: "Typography", link: "/typography" },
          ],
        },
      ],
      menuIcons: [
        { iconClass: "fa-solid fa-magnifying-glass", link: "/search" },
        { iconClass: "fa-solid fa-list", link: "/menu" },
      ],
      index: 0,
    };
  },
  components: {
    Menu,
  },
  methods: {
    imgPlus() {
      if (this.index < this.headerImg.length - 1) {
        return this.index++;
      } else {
        this.index = 0;
      }
    },
    imgMinus() {
      if (this.index > 0) {
        return this.index--;
      } else {
        this.index = this.headerImg.length - 1;
      }
    },
  },
};
</script>

<template>
  <div class="container">
    <Menu :menuItems="menuItems" :menuIcons="menuIcons" />
    <!-- sezione immagini -->
    <div class="images">
      <div class="rev">
        <img :src="headerImg[index].logoImg" alt="" />
      </div>
      <div class="info">
        <h1>
          {{ headerImg[index].info }}
        </h1>
        <p>{{ headerImg[index].description }}</p>
        <button>
          <span>Read More</span><span>|</span
          ><i class="fa fa-arrow-right-long"></i>
        </button>
        <button>
          <span>Purchase</span><span>|</span
          ><i class="fa fa-arrow-right-long"></i>
        </button>
      </div>
      <div class="arrow-right">
        <i @click="imgPlus()" class="fa fa-arrow-right-long fa-2x"></i>
      </div>
      <div class="arrow-left">
        <i @click="imgMinus()" class="fa fa-arrow-left-long fa-2x"></i>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@import "/src/assets/scss/general.scss";
@import "/src/assets/scss/base/variabili.scss";
@import "/src/assets/scss/base/mixin.scss";

// sezione immagini header
.rev img {
  max-width: 100%;
}
.images {
  position: relative;
}
.arrow-right {
  position: absolute;
  top: 50%;
  right: 30px;
}
.arrow-left {
  position: absolute;
  top: 50%;
  left: 30px;
}
.arrow-right:hover {
  position: absolute;
  top: 50%;
  right: 25px;
}
.arrow-left:hover {
  position: absolute;
  top: 50%;
  left: 25px;
}
.info {
  position: absolute;
  top: 30%;
  width: 600px;
  left: 15%;
  font-size: xx-large;
}
.info h1::after {
  content: "";
  display: inline-block;
  width: 10px;
  height: 10px;
  background-color: #ff4612;
  border-radius: 50%;
  margin-left: 10px;
  vertical-align: baseline;
}

.info p {
  color: gray;
}
// modifiche generali per button
.info button:nth-of-type(1) {
  background-color: white;
  color: black;
  border: 1px solid #ccc;
  padding: 10px 20px;
  font-size: large;
  margin-top: 25px;
  margin-right: 20px;
  cursor: pointer;
}
.info button:nth-of-type(1) {
  @include button-white;
}

.info button:nth-of-type(2) {
  @include button-orange;
}
</style>
