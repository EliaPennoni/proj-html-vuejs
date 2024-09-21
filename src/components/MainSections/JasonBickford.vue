<script>
export default {
  data() {
    return {
      JasonImg: [
        {
          logoImg: "/teach/img/h1-blog-img-04.jpg",
        },
        {
          logoImg: "/teach/img/h1-img-02.jpg",
        },
        {
          logoImg: "/teach/img/h1-img-03.jpg",
        },
      ],
      index: 0,
    };
  },
  methods: {
    imgPlus() {
      if (this.index < this.JasonImg.length - 1) {
        return this.index++;
      } else {
        this.index = 0;
      }
    },
    imgMinus() {
      if (this.index > 0) {
        return this.index--;
      } else {
        this.index = this.JasonImg.length - 1;
      }
    },
  },
};
</script>

<template>
  <div class="background">
    <div class="container">
      <div class="images">
        <div class="rev">
          <img :src="JasonImg[index].logoImg" alt="" />
          <div class="button">
            <div class="arrow-left">
              <i @click="imgMinus()" class="fa fa-arrow-left-long"></i>
            </div>
            <div class="arrow-right">
              <i @click="imgPlus()" class="fa fa-arrow-right-long"></i>
            </div>
          </div>
        </div>
        <div class="bickford">
          <h3>Jason Bickford</h3>
          <span>Founder and Executive Director</span>
          <p>
            Lorem ipsum dolor sit amet, consectetur adipisicing elit. Suscipit,
            corrupti.
          </p>
          <span>
            <div class="link">
              <a href=""><i class="fa-brands fa-linkedin"></i></a>
              <a href=""><i class="fa-brands fa-facebook"></i></a>
              <a href=""><i class="fa-brands fa-twitter"></i></a>
            </div>
            <p>Jason Bickford</p>
          </span>
        </div>
        <img class="pixel" src="/teach/svg/svg-4.svg" alt="" />
      </div>
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
  width: 80%;
  height: 600px;
  margin: 0 auto;
  background-color: #fafafa;
  display: flex;
  align-items: center;
}
.images {
  padding: 30px;
  position: relative;
}
.button {
  display: flex;
  position: absolute;
  bottom: 5px;
  left: 0;
}
.button div i {
  background-color: #ff4612;
  color: white;
  padding: 20px;
}
.rev {
  max-width: 60%;
  position: relative;
}
.rev img {
  max-width: 100%;
  height: auto;
  object-fit: cover;
}
.pixel {
  position: absolute;
  top: -50px;
  right: -100px;
}
.bickford {
  position: absolute;
  top: 25%;
  left: 50%;
  z-index: 999;
  background-color: white;
  padding: 30px;
  width: 500px;
}
.bickford h3 {
  font-family: "TuesdayNight", serif;
  font-size: 25px;
  margin-bottom: 5px;
}
.bickford p {
  margin-top: 20px;
}
.bickford span:first-of-type {
  color: gray;
  margin-bottom: 30px;
}
.bickford span::after {
  content: "";
  display: inline-block;
  width: 60px;
  height: 2px;
  background-color: #ff4612;
  position: absolute;
  bottom: 100px;
  right: 82%;
}
.bickford span:last-of-type {
  display: flex;
  justify-content: space-between;
}
.bickford span:last-of-type i {
  color: #ff4612;
  text-decoration: none;
  margin-right: 10px;
  margin-top: 30px;
}
.bickford span:last-of-type i:hover {
  color: black;
}
.bickford span:last-of-type p {
  font-family: "MyFont", sans-serif;
  color: #ff4612;
  font-size: 30px;
}
</style>
