<script>
export default {
  data() {
    return {
      cards: [
        {
          title: "New Business Day",
          description:
            "Lorem ipsum dolor sit amet consectetur adipisicing elit. Accusantium, unde!",
          img: "/public/teach/img/h1-blog-img-01.jpg",
        },
        {
          title: "Boost Motivation",
          description:
            "Lorem ipsum dolor sit amet consectetur adipisicing elit. Accusantium, unde!",
          img: "/public/teach/img/h1-blog-img-02.jpg",
        },
        {
          title: "Next Investment",
          description:
            "Lorem ipsum dolor sit amet consectetur adipisicing elit. Accusantium, unde!",
          img: "/public/teach/img/h1-blog-img-03.jpg",
        },
        {
          title: "Team Building",
          description:
            "Lorem ipsum dolor sit amet consectetur adipisicing elit. Accusantium, unde!",
          img: "/public/teach/img/h1-blog-img-04.jpg",
        },
      ],
      currentIndex: 0,
      visibleCardsCount: 3,
    };
  },
  computed: {
    visibleCards() {
      return this.cards.slice(
        this.currentIndex,
        this.currentIndex + this.visibleCardsCount
      );
    },
  },
  methods: {
    next() {
      if (this.currentIndex < this.cards.length - this.visibleCardsCount) {
        this.currentIndex++;
      } else {
        this.currentIndex = 0;
      }
    },
    prev() {
      if (this.currentIndex > 0) {
        this.currentIndex--;
      } else {
        this.currentIndex = this.cards.length - this.visibleCardsCount;
      }
    },
  },
};
</script>



<template>
  <div class="background">
    <div class="container">
      <img class="pixel" src="/teach/svg/svg-4.svg" alt="" />
      <h3>Latest News</h3>
      <p>Lorem ipsum dolor sit amet consectetur adipisicing elit.</p>

      <div class="carousel-container">
        <div class="carousel">
          <div
            class="cards"
            :style="{
              transform: `translateX(-${
                currentIndex * (100 / visibleCardsCount)
              }%)`,
            }"
          >
            <div v-for="(card, index) in cards" :key="index" class="card">
              <img :src="card.img" alt="" />
              <span>
                <i class="fa-regular fa-clock fa-sm"></i>
                <a href="">May 5, 2019</a>
                <i class="fa-regular fa-user fa-sm"></i>
                <a href="">Amanda Doe</a>
              </span>
              <button><i class="fa-solid fa-tag"></i> Business, Leading</button>
              <h4>{{ card.title }}</h4>
              <p>{{ card.description }}</p>
              <span class="arrow-more">Read More</span>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="arrow-left">
      <i @click="prev" class="fa-solid fa-arrow-left-long"></i>
    </div>
    <div class="arrow-right">
      <i @click="next" class="fa-solid fa-arrow-right-long"></i>
    </div>
  </div>
</template>
  
  
<style lang="scss" scoped>
@use "/src/assets/scss/general.scss" as *;
.background {
  background-color: #fafafa;
  width: 100%;
  position: relative;
}

.container {
  background-color: #fafafa;
  width: 80%;
  margin: 0 auto;
  padding: 20px;
  position: relative;
}
.pixel {
  position: absolute;
  top: -10%;
}
.container h3,
.container p {
  text-align: center;
  z-index: 2;
}
.container h3 {
  font-family: "Libre Baskerville", serif;
  margin-bottom: 20px;
  text-align: center;
  font-size: 40px;
  font-weight: 600;
  position: relative;
}
.container > p {
  text-align: center;
  margin-bottom: 30px;
  position: relative;
}
.container p {
  margin-bottom: 30px;
}
.container h3::after {
  content: "";
  display: inline-block;
  width: 5px;
  height: 5px;
  background-color: #ff4612;
  border-radius: 50%;
  margin-left: 3px;
  vertical-align: baseline;
}
.container p::before {
  content: "";
  display: inline-block;
  width: 60px;
  height: 2px;
  background-color: #ff4612;
  position: absolute;
  bottom: -20px;
  left: 47%;
}

.carousel-container {
  position: relative;
  width: 100%;
  overflow: hidden;
}

.carousel {
  display: flex;
  width: 100%;
  position: relative;
  overflow: hidden;
}

.cards {
  display: flex;
  width: 100%;
  transition: transform 0.5s ease;
}

.card {
  width: calc(((100% / 3) - 10px));
  flex-shrink: 0;
  padding: 20px;
  margin: 10px;
  text-align: center;
  position: relative;
}
.card {
  position: relative;
}
.card p::before {
  content: "";
  display: inline-block;
  width: 60px;
  height: 2px;
  background-color: #ff4612;
  position: absolute;
  bottom: 50px;
  left: 130px;
}

.arrow-left,
.arrow-right {
  position: absolute;
  top: 50%;
  cursor: pointer;
  z-index: 10;
}

.arrow-left {
  left: 120px;
}

.arrow-right {
  right: 80px;
}

.cards {
  display: flex;
  transition: transform 0.5s ease;
}

.card button {
  position: absolute;
  top: 42%;
  right: 40px;
  padding: 8px;
  background-color: #ff4612;
  border: none;
  color: white;
  font-size: small;
}
.card h4 {
  font-size: xx-large;
  font-family: "Libre Baskerville", serif;
  margin-bottom: 20px;
  margin-top: 5px;
}
.card img {
  width: 100%;
  margin-bottom: 30px;
}

.carousel-btn {
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  color: white;
  border: none;
  padding: 10px;
  cursor: pointer;
  z-index: 10;
}

.carousel-btn.left {
  left: 10px;
}

.carousel-btn.right {
  right: 10px;
}

.carousel-btn:hover {
  background-color: #333;
}
.card span i {
  margin-right: 3px;
  color: #ff4612;
}
.card span a {
  font-size: 15px;
  margin-right: 10px;
  text-decoration: none;
  color: black;
}
.card span a:hover {
  color: #ff4612;
}
.arrow-more {
  display: inline-block;
  position: relative;
  font-size: 16px;
  font-weight: bold;
  color: #333;
  text-decoration: none;
  transition: transform 0.3s ease;
}
.arrow-more:hover {
  transform: translateX(30px);
}
.arrow-more::before {
  content: "\2192";
  position: absolute;
  left: -20px;
  opacity: 0;
  transition: opacity 0.3s ease;
  color: #ff4612;
}

.arrow-more:hover::before {
  opacity: 1;
}
</style>
