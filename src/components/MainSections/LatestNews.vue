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
      currentIndex: 0, // Indice attuale, inizia con 0
    };
  },
  computed: {
    visibleCards() {
      // Ritorna solo le 3 card visibili in base all'indice corrente
      return this.cards.slice(this.currentIndex, this.currentIndex + 3);
    },
  },
  methods: {
    next() {
      // Aumenta l'indice solo se ci sono altre card da mostrare
      if (this.currentIndex < this.cards.length - 3) {
        this.currentIndex++;
      }
    },
    prev() {
      // Riduci l'indice solo se non siamo già alla prima card
      if (this.currentIndex > 0) {
        this.currentIndex--;
      }
    },
  },
};
</script>



<template>
  <div class="background">
    <div class="container">
      <h3>Latest News</h3>
      <p>Lorem ipsum dolor sit amet consectetur adipisicing elit.</p>
      <div class="carousel-container">
        <div class="carousel">
          <div class="cards">
            <div
              v-for="(card, index) in visibleCards"
              :key="index"
              class="card"
            >
              <img :src="card.img" alt="" />
              <span
                ><i class="fa-regular fa-clock fa-sm"
                  ><a href="">May 5, 2019</a></i
                ><i class="fa-regular fa-user fa-sm"
                  ><a href="">Amanda Doe</a></i
                ></span
              >
              <h3>{{ card.title }}</h3>
              <p>{{ card.description }}</p>
            </div>
          </div>
        </div>

        <button @click="prev" class="carousel-btn left">&lt;</button>
        <button @click="next" class="carousel-btn right">&gt;</button>
      </div>
    </div>
  </div>
</template>
  
<style lang="scss" scoped>
@use "/src/assets/scss/general.scss" as *;
.background {
  background-color: #fafafa;
  width: 100%;
}

.container {
  background-color: #fafafa;
  width: 80%;
  margin: 0 auto;
  padding: 20px;
}
.container h3 {
  font-size: 35px;
  font-family: "Libre Baskerville", serif;
  margin-bottom: 20px;
  text-align: center;
}
.container p {
  text-align: center;
  margin-bottom: 60px;
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

.carousel-container {
  position: relative;
  width: 100%;
  overflow: hidden; /* Nasconde le card extra */
}

.carousel {
  display: flex;
  width: 100%;
}

.cards {
  display: flex;
  transition: transform 0.5s ease; /* Transizione fluida per lo scorrimento */
}

.card {
  width: calc(100% / 3); /* Ogni card ha larghezza fissa, per mostrare 3 card */
  padding: 20px;
  background-color: #f5f5f5;
  margin: 10px;
  text-align: center;
  border: 1px solid #ddd;
}
.card img {
  width: 100%;
}

.carousel-btn {
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  background-color: #ff4612;
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
  margin-right: 5px;
}
.card span i a {
  font-size: 10px;
  margin-left: 5px;
  margin-right: 5px;
  text-decoration: none;
  color: black;
}
.card span i a:hover {
  color: #ff4612;
}
</style>
