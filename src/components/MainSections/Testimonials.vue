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
      <div class="faces">
        <div class="images">
          <img :src="headerImg[index].logoImg" alt="" />
        </div>
        <div class="info">
          <h1>
            {{ headerImg[index].info }}
          </h1>
          <p>{{ headerImg[index].description }}</p>
        </div>
        <div class="arrow-right">
          <i @click="imgPlus()" class="fa fa-arrow-right-long fa-2x"></i>
        </div>
        <div class="arrow-left">
          <i @click="imgMinus()" class="fa fa-arrow-left-long fa-2x"></i>
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@use "/src/assets/scss/general.scss" as *;
.background {
  background-color: #1e1c1c;
  width: 100%;
}
.container {
  width: 80%;
  margin: 0 auto;
  padding: 20px;
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
.faces {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  text-align: center;
  color: white;
  width: 80%;
  margin: 0 auto;
  position: relative;
  transition: transform 0.5s ease;
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
