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
      visibleCardsCount: 3,
    };
  },
  computed: {
    visibleCards() {
      // Ritorna solo le 3 card visibili in base all'indice corrente
      return this.cards.slice(
        this.currentIndex,
        this.currentIndex + this.visibleCardsCount
      );
    },
  },
  methods: {
    next() {
      // Aumenta l'indice solo se ci sono altre card da mostrare
      if (this.currentIndex < this.cards.length - this.visibleCardsCount) {
        this.currentIndex++;
      } else {
        this.currentIndex = 0;
      }
    },
    prev() {
      // Riduci l'indice solo se non siamo già alla prima card
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
          <!-- Aggiungi il `translateX` per spostare il blocco delle card -->
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
                <i class="fa-regular fa-clock fa-sm"
                  ><a href="">May 5, 2019</a></i
                >
                <i class="fa-regular fa-user fa-sm"
                  ><a href="">Amanda Doe</a></i
                >
              </span>
              <button><i class="fa-solid fa-tag"></i> Business, Leading</button>
              <h4>{{ card.title }}</h4>
              <p>{{ card.description }}</p>
              <span>Read More</span>
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
  position: relative;
}
.pixel {
  position: absolute;
  top: -10%;
}
.container h3,
.container p {
  position: relative; /* Non serve z-index, l'immagine si posiziona sotto */
  text-align: center;
  z-index: 2; /* Assicurati che siano sopra l'immagine */
}
.container h3 {
  font-family: "Libre Baskerville", serif;
  margin-bottom: 20px;
  text-align: center;
  font-size: 40px;
  font-weight: 600;
}
.container > p {
  text-align: center;
  margin-bottom: 30px;
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

.carousel-container {
  position: relative;
  width: 100%;
  overflow: hidden; /* Nasconde le card extra */
}

.carousel {
  display: flex;
  width: 100%;
  position: relative;
  overflow: hidden; /* Nasconde le card extra */
}

.cards {
  display: flex;
  width: 100%; /* Fa in modo che le card si dispongano in fila */
  transition: transform 0.5s ease; /* Aggiungi transizione per uno scorrimento fluido */
}

.card {
  width: calc(((100% / 3) - 10px));
  flex-shrink: 0; /* Mantiene la larghezza della card costante */
  padding: 20px;
  margin: 10px;
  text-align: center;
  position: relative;
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

.cards {
  display: flex;
  transition: transform 0.5s ease; /* Transizione fluida per lo scorrimento */
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
