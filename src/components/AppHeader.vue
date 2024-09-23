<script>
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
  <div class="container">
    <nav>
      <div class="logo">
        <a href="">
          <img src="/teach/img/logo-img-01.png" alt="" />
        </a>
      </div>
      <div class="list">
        <ul>
          <li class="active"><a href="">homes</a></li>
          <li><a href="">pages</a></li>
          <li><a href="">blog</a></li>
          <li><a href="">shop</a></li>
          <li><a href="">events</a></li>
          <li><a href="">elements</a></li>
          <div class="icon">
            <span>
              <a href=""><i class="fa-solid fa-magnifying-glass"></i></a>
            </span>
            <span>
              <a href=""><i class="fa-solid fa-list"></i></a>
            </span>
          </div>
        </ul>
      </div>
    </nav>
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
          <span>Read More |</span><i class="fa fa-arrow-right-long"></i>
        </button>
        <button>
          <span>Purchase |</span><i class="fa fa-arrow-right-long"></i>
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
@use "/src/assets/scss/general.scss" as *;

.container {
  width: 100%;
  position: relative;
}

nav {
  display: flex;
  justify-content: space-between;
  align-items: center;
  width: 100%;
  position: absolute;
  top: 10px;
  z-index: 999;
  padding: 30px;
}
.logo img {
  max-height: 100px;
  max-width: 150px;
}

.list ul {
  display: flex;
  list-style: none;
}
.list ul li {
  position: relative;
}
.list ul li a {
  text-decoration: none;
  margin-left: 15px;
  margin-right: 15px;
  font-size: medium;
  font-weight: bold;
  color: black;
  text-transform: uppercase;
  position: relative;
}

.list ul li a::before {
  content: "\f178";
  font-family: "Font Awesome 5 Free";
  font-weight: 900;
  position: absolute;
  left: -20px;
  top: 50%;
  transform: translateY(-50%);
  opacity: 0;
  transition: opacity 0.5s ease, left 0.5s ease;
}

.list ul li a:hover::before {
  opacity: 1;
}

.list ul li a:hover {
  color: #ff4612;
}
/* Stile per l'elemento attivo */
.list ul li.active a {
  color: #ff4612; /* Colore del testo dell'elemento attivo */
}

.list ul li.active a::before {
  opacity: 1; /* La freccia sarà sempre visibile */
  left: -20px; /* Mantieni la posizione della freccia */
}
.icon span a {
  margin-left: 15px;
  margin-right: 15px;
  color: black;
}
.icon span a:hover {
  color: #ff4612;
}
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
.info button:nth-of-type(1) {
  background-color: white;
  color: black;
  border: 1px solid #ccc;
  padding: 15px 25px;
  font-size: large;
  margin-top: 25px;
  margin-right: 20px;
}

.info button:nth-of-type(2) {
  background-color: #ff4612;
  color: white; /* Testo bianco per contrastare lo sfondo arancione */
  border: none; /* Rimuovi bordo se non necessario */
  padding: 15px 25px;
  font-size: large;
  margin-top: 25px;
}
</style>
