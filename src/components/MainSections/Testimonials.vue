<script>
export default {
  data() {
    return {
      headerImg: [
        {
          logoImg: "/teach/img/h3-img-04.png",
          info: "Cynthia Clark",
          description:
            "Lorem ipsum, dolor sit amet consectetur adipisicing elit. Illo, odio illum. Ut delectus voluptas, tempora modi atque harum cumque deserunt?",
        },
        {
          logoImg: "/teach/img/h3-img-07.png",
          info: "Clarice Hastings",
          description:
            "Lorem ipsum, dolor sit amet consectetur adipisicing elit. Illo, odio illum. Ut delectus voluptas, tempora modi atque harum cumque deserunt?",
        },
        {
          logoImg: "/teach/img/h3-img-08.png",
          info: "Brenda Kelly",
          description:
            "Lorem ipsum, dolor sit amet consectetur adipisicing elit. Illo, odio illum. Ut delectus voluptas, tempora modi atque harum cumque deserunt?",
        },
      ],
      index: 0,
    };
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
  <div class="background">
    <div class="container">
      <div class="letters">
        <span>T</span>
        <span>E</span>
        <span>S</span>
        <span>T</span>
        <span>I</span>
        <span>M</span>
        <span>O</span>
        <span>N</span>
        <span>I</span>
        <span>A</span>
        <span>L</span>
        <span>S</span>
      </div>
      <!-- Bootstrap Carousel -->
      <div
        id="carouselExampleIndicators"
        class="carousel slide"
        data-bs-ride="carousel"
      >
        <!-- Carousel Indicators -->
        <div class="carousel-indicators">
          <button
            v-for="(item, idx) in headerImg"
            :key="idx"
            type="button"
            :data-bs-target="'#carouselExampleIndicators'"
            :data-bs-slide-to="idx"
            :class="{ active: idx === 0 }"
            :aria-label="'Slide ' + (idx + 1)"
            :aria-current="idx === 0 ? 'true' : false"
          ></button>
        </div>

        <!-- Carousel Items -->
        <div class="carousel-inner">
          <div
            v-for="(item, idx) in headerImg"
            :key="idx"
            :class="['carousel-item', { active: idx === 0 }]"
          >
            <img
              :src="item.logoImg"
              class="d-block w-10 mx-auto"
              :alt="item.info"
            />
            <div class="carousel-caption d-none d-md-block">
              <h5>{{ item.info }}</h5>
              <p>{{ item.description }}</p>
            </div>
          </div>
        </div>

        <!-- Carousel Controls -->
        <button
          class="carousel-control-prev"
          type="button"
          data-bs-target="#carouselExampleIndicators"
          data-bs-slide="prev"
        >
          <span class="carousel-control-prev-icon" aria-hidden="true"></span>
          <span class="visually-hidden">Previous</span>
        </button>
        <button
          class="carousel-control-next"
          type="button"
          data-bs-target="#carouselExampleIndicators"
          data-bs-slide="next"
        >
          <span class="carousel-control-next-icon" aria-hidden="true"></span>
          <span class="visually-hidden">Next</span>
        </button>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@use "/src/assets/scss/general.scss" as *;
// Import all of Bootstrap's CSS
@import "bootstrap/scss/bootstrap";
.background {
  background-color: #1e1c1c;
  width: 100%;
  height: 500px;
}
.container {
  width: 100%;
  height: 100%;
  margin: 0 auto;
  padding: 20px;
}
.carousel-inner {
  position: relative;
  overflow: visible; /* Sovrascrive il valore di overflow hidden */
}
.carousel-item {
  position: relative;
}
.carousel-caption {
  position: absolute;
  bottom: -150px;
}
.carousel-indicators {
  position: absolute;
  bottom: -180px;
}

.letters {
  display: flex;
  justify-content: center; /* Centra gli span orizzontalmente */
  align-items: center; /* Centra gli span verticalmente */
  background-color: #1e1c1c;
  width: 80%;
  margin: 0 auto;
  padding: 20px;
}
.letters span {
  background-color: #1e1c1c;
  color: #181515;
  font-size: 120px;
  font-family: "Libre Baskerville", serif;
  font-weight: 700;
}
.arrow-left,
.arrow-right {
  position: absolute;
  top: 50%;
  cursor: pointer;
  z-index: 10;
}

.arrow-left {
  left: 0px;
}

.arrow-right {
  right: 0px;
}
</style>
