
  <script>
export default {
  data() {
    return {
      images: [
        {
          src: "/public/teach/img/5005001.png",
          alt: "Image 1",
          name: "Sandra Harvey",
          role: "Instructor",
        },
        {
          src: "/public/teach/img/h1-img-03.jpg",
          alt: "Image 2",
          name: "Ruth Hunter",
          role: "Manager",
        },
        {
          src: "/public/teach/img/black-teacher.jpg",
          alt: "Image 3",
          name: "Maya Adams",
          role: "Nutritionist",
        },
        {
          src: "/public/teach/img/h1-blog-img-04.jpg",
          alt: "Image 4",
          name: "Christine Yin",
          role: "Founder",
        },
        {
          src: "/public/teach/img/download.jfif",
          alt: "Image 5",
          name: "Stephen Griffin",
          role: "Life Coach",
        },
      ],
      currentIndex: 0,
      visibleImagesCount: 3, // Numero di immagini visibili
    };
  },
  methods: {
    next() {
      if (this.currentIndex < this.images.length - this.visibleImagesCount) {
        this.currentIndex++;
      } else {
        this.currentIndex = 0; // Ricomincia dalla prima immagine
      }
    },
    prev() {
      if (this.currentIndex > 0) {
        this.currentIndex--;
      } else {
        this.currentIndex = this.images.length - this.visibleImagesCount;
      }
    },
  },
};
</script>

<template>
  <div class="background">
    <img class="pixel" src="/teach/svg/svg-4.svg" alt="" />
    <div class="carousel-container">
      <h3>We can teach you</h3>
      <p>Lorem ipsum dolor sit amet consectetur adipisicing elit.</p>
      <div class="carousel-wrapper">
        <!-- Carosello delle immagini con transizione -->
        <div
          class="carousel"
          :style="{
            transform: `translateX(-${
              currentIndex * (100 / visibleImagesCount)
            }%)`,
          }"
        >
          <div
            v-for="(image, index) in images"
            :key="index"
            class="carousel-image"
          >
            <img :src="image.src" :alt="image.alt" />

            <div class="links">
              <button><i class="fa-solid fa-share-nodes"></i></button>
              <div class="link">
                <a href=""><i class="fa-brands fa-linkedin"></i></a>
                <a href=""><i class="fa-brands fa-facebook"></i></a>
                <a href=""><i class="fa-brands fa-twitter"></i></a>
              </div>
            </div>

            <div class="image-info">
              <h3>{{ image.name }}</h3>
              <p>{{ image.role }}</p>
            </div>
          </div>
        </div>
      </div>
    </div>
    <span class="arrow arrow-left">
      <i @click="prev" class="fa fa-arrow-left fa-2x"></i>
    </span>
    <span class="arrow arrow-right">
      <i @click="next" class="fa fa-arrow-right fa-2x"></i>
    </span>
  </div>
</template>
  
  <style scoped>
.background {
  position: relative;
}
.carousel-container {
  position: relative;
  width: 80%;
  margin: 0 auto;
  overflow: hidden;
}
.carousel-container > h3 {
  font-family: "Libre Baskerville", serif;
  margin-bottom: 20px;
  text-align: center;
  font-size: 40px;
  font-weight: 600;
}
.carousel-container > p {
  font-family: "Libre Baskerville", serif;
  margin-bottom: 20px;
  text-align: center;
  font-size: 20px;
  color: gray;
}

.carousel-wrapper {
  width: 100%;
  z-index: 2;
}

.carousel {
  display: flex;
  transition: transform 0.5s ease-in-out;
}

.carousel-image {
  flex: 1 0 33.33%;
  display: flex;
  flex-direction: column;
  padding: 10px;
  position: relative;
}

.carousel-image img {
  width: 100%;
  height: 350px;
  border-radius: 5px;
  object-fit: cover;
}

.image-info {
  margin-top: 10px;
}
.image-info h3 {
  margin-top: 10px;
  font-family: "Libre Baskerville", serif;
  font-size: 30px;
}
.image-info p {
  color: gray;
}

.arrow-right {
  position: absolute;
  top: 50%;
  right: 80px;
  transform: translateY(-50%);
  color: black;
  border: none;
  cursor: pointer;
  padding: 10px;
}
.arrow-left {
  position: absolute;
  top: 50%;
  left: 80px;
  transform: translateY(-50%);
  color: black;
  border: none;
  cursor: pointer;
  padding: 10px;
}

.carousel-container > h3::after {
  content: "";
  display: inline-block;
  width: 5px;
  height: 5px;
  background-color: #ff4612;
  border-radius: 50%;
  margin-left: 3px;
  vertical-align: baseline;
}
.carousel-container p::before {
  content: "";
  display: inline-block;
  width: 60px;
  height: 2px;
  background-color: #ff4612;
  position: absolute;
  bottom: -30px;
  right: 50%;
}

.pixel {
  position: absolute;
  top: -200px;
}

.links {
  display: flex;
  flex-direction: row-reverse;
  align-items: center;
  position: absolute;
  bottom: 80px;
  left: 150px;
}

.link {
  opacity: 0;
  transition: opacity 0.3s ease;
}

.links:hover .link {
  opacity: 1;
}

button,
.link a {
  display: inline-block;
  background-color: #ff4612;
  border: none;
  padding: 10px 20px; /* Uniforma il padding */
  color: white;
  text-align: center;
  cursor: pointer;
  transition: background-color 0.3s ease;
  font-size: 16px; /* Stesso font-size */
  line-height: 1.5; /* Allinea il testo verticalmente */
  height: 40px; /* Assicura che l'altezza sia la stessa */
  width: 40px; /* Aggiungi questa se vuoi una larghezza uniforme */
}

button:hover,
.link a:hover {
  background-color: #333;
}

button,
.link a {
  border-radius: 5px;
}

.link a {
  text-decoration: none;
}
</style>
  