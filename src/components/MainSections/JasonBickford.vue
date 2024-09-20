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
        <img class="pixel" src="/teach/svg/svg-4.svg" alt="" />
        <div class="bickford">
          <h3>Jason Bickford</h3>
          <span>Founder and Executive Director</span>
          <p>
            Lorem ipsum dolor sit amet, consectetur adipisicing elit. Suscipit,
            corrupti.
          </p>
          <span>
            <a href=""></a>
            <a href=""></a>
            <a href=""></a>
            <img src="" alt="" />
          </span>
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
  max-width: 50%;
  position: relative;
}
.rev img {
  max-width: 100%;
}
.pixel {
  position: absolute;
  top: 0;
  right: 0;
}
.bickford {
  position: absolute;
  top: 50%;
  left: 40%;
  z-index: 999;
  background-color: white;
  padding: 30px;
}
</style>
