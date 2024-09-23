<script>
export default {
  data() {},
  methods: {},
};
</script>

<template>
  <div class="background">
    <img src="/public/teach/img/h1-img-08.jpg" alt="" />
    <div class="title">
      <h3>Pricing Plan</h3>
      <p>Lorem ipsum dolor sit amet consectetur adipisicing elit.</p>
    </div>

    <div class="plans">
      <div class="plan1">
        <h4>Basic Plan</h4>
        <span class="price">100</span>
        <span>$</span>
        <ul>
          <li>
            <i class="fa-solid fa-check"></i>
            <span>Lorem ipsum dolor sit amet consectetur</span>
          </li>
          <li>
            <i class="fa-solid fa-check"></i>
            <span>Lorem ipsum dolor sit amet consectetur</span>
          </li>
          <li>
            <i class="fa-solid fa-check"></i>
            <span>Lorem ipsum dolor sit amet consectetur</span>
          </li>
        </ul>
        <button>
          <span>Purchase</span><i class="fa fa-arrow-right fa-2x"></i>
        </button>
      </div>
      <div class="plan2">
        <h4>Premium Plan</h4>
        <span class="price">200</span>
        <span>$</span>
        <ul>
          <li>
            <i class="fa-solid fa-check"></i>
            <span>Lorem ipsum dolor sit amet consectetur</span>
          </li>
          <li>
            <i class="fa-solid fa-check"></i>
            <span>Lorem ipsum dolor sit amet consectetur</span>
          </li>
          <li>
            <i class="fa-solid fa-check"></i>
            <span>Lorem ipsum dolor sit amet consectetur</span>
          </li>
        </ul>
        <button>
          <span>Purchase</span><i class="fa fa-arrow-right fa-2x"></i>
        </button>
      </div>
      <div class="plan3">
        <h4>Deluxe Plan</h4>
        <span class="price">300</span>
        <span>$</span>
        <ul>
          <li>
            <i class="fa-solid fa-check"></i>
            <span>Lorem ipsum dolor sit amet consectetur</span>
          </li>
          <li>
            <i class="fa-solid fa-check"></i>
            <span>Lorem ipsum dolor sit amet consectetur</span>
          </li>
          <li>
            <i class="fa-solid fa-check"></i>
            <span>Lorem ipsum dolor sit amet consectetur</span>
          </li>
        </ul>
        <button>
          <span>Purchase</span><i class="fa fa-arrow-right fa-2x"></i>
        </button>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@use "/src/assets/scss/general.scss" as *;

.background {
  width: 100%;
  height: 100vh;
  position: relative;
}

.background img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  position: absolute;
  top: 0;
  left: 0;
  z-index: -1;
}

.plans {
  width: 80%;
  margin: 0 auto;
  display: flex;
  justify-content: space-around;
  position: absolute;
  top: 60%;
  left: 50%;
  transform: translate(-50%, -50%);
  z-index: 1;
}
.plans h4 {
  position: relative;
}
.plans h4::after {
  content: "";
  display: inline-block;
  width: 5px;
  height: 5px;
  background-color: #ff4612;
  border-radius: 50%;
  margin-left: 3px;
  vertical-align: baseline;
}

.title {
  text-align: center;
  position: absolute;
  top: 15%;
  left: 50%;
  transform: translateX(-50%);
  z-index: 1;
  color: white;
}
.title h3 {
  font-size: 40px;
  font-family: "Libre Baskerville", serif;
  font-weight: 600;
}
.plan1,
.plan3 {
  background-color: white;
}
.plan2 {
  background-color: black;
  color: white;
}
.plan1 .price,
.plan2 .price,
.plan3 .price {
  font-size: 40px;
  font-family: "Libre Baskerville", serif;
  font-weight: 700;
}
.plan1 h4,
.plan2 h4,
.plan3 h4 {
  font-size: 20px;
  font-family: "Libre Baskerville", serif;
  font-weight: 600;
}
.plan1,
.plan2,
.plan3 {
  padding: 30px;
  margin-right: 10px;
  border-radius: 10px;
}
.plan1 ul,
.plan2 ul,
.plan3 ul {
  list-style: none;
  font-size: small;
  margin-top: 15px;
}
.plan1 ul li,
.plan2 ul li,
.plan3 ul li {
  list-style: none;
  font-size: small;
  margin-top: 15px;
  margin-bottom: 30px;
}
.plan1 ul li i,
.plan2 ul li i,
.plan3 ul li i {
  margin-right: 3px;
}
.plan1 span:last-of-type,
.plan2 span:last-of-type,
.plan3 span:last-of-type {
  vertical-align: super;
}
button {
  display: block;
  background-color: #ff4612;
  color: white;
  border: none;
  margin-top: 30px;
  margin-bottom: 30px;
  padding: 15px;
  display: flex;
  align-items: center;
}
button span {
  font-size: medium;
  margin-right: 5px;
}
</style>
