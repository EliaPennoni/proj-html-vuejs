<script>
export default {
  data() {
    return {
      cards: [
        {
          img: "teach/svg/svg-0.svg",
          subtitle: "knowing",
          text: "Lorem ipsum, dolor sit amet consectetur adipisicing elit. Illo, odio illum",
        },
        {
          img: "teach/svg/svg-1.svg",
          subtitle: "Selling",
          text: "Lorem ipsum, dolor sit amet consectetur adipisicing elit. Illo, odio illum",
        },
        {
          img: "teach/svg/svg-2.svg",
          subtitle: "Learning",
          text: "Lorem ipsum, dolor sit amet consectetur adipisicing elit. Illo, odio illum",
        },
        {
          img: "teach/svg/svg-3.svg",
          subtitle: "Contact",
          text: "Lorem ipsum, dolor sit amet consectetur adipisicing elit. Illo, odio illum",
        },
      ],
    };
  },
  methods: {},
};
</script>

<template>
  <main>
    <div class="container">
      <div class="titolo">
        <h2>Our Specialties</h2>
        <p>
          Lorem ipsum, dolor sit amet consectetur adipisicing elit. Illo, odio
          illum.
        </p>
      </div>
      <div class="cards">
        <div v-for="(card, index) in cards" :key="index" class="card">
          <div class="img">
            <a href=""><img :src="card.img" alt="card" /></a>
          </div>
          <div class="subtitle">
            <a href="">
              <h4>{{ card.subtitle }}</h4>
            </a>
          </div>
          <div class="info">
            <p>{{ card.text }}</p>
          </div>
        </div>
      </div>
    </div>
  </main>
</template>

<style lang="scss" scoped>
@use "/src/assets/scss/general.scss" as *;

.container {
  width: 80%;
  margin: 0 auto;
}
.titolo h2,
p {
  text-align: center;
}
.titolo h2 {
  font-size: 50px;
}
.titolo h2::after {
  content: "";
  display: inline-block;
  width: 10px;
  height: 10px;
  background-color: #ff4612;
  border-radius: 50%;
  margin-left: 3px;
  vertical-align: baseline;
}
.titolo p {
  font-size: x-large;
  color: grey;
  margin-bottom: 80px;
  margin-top: 10px;
  position: relative;
}
.titolo p::after {
  content: "";
  display: inline-block;
  width: 60px;
  height: 2px;
  background-color: #ff4612;
  position: absolute;
  bottom: -30px;
  right: 50%;
}
.cards {
  display: flex;
  justify-content: space-around;
}

.card {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin-right: 20px;
  margin-left: 20px;
}
.card h4 {
  margin-top: 10px;
  margin-bottom: 10px;
  font-weight: bold;
  font-size: 20px;
  color: black;
  text-decoration: none;
}
.card a {
  text-decoration: none;
}
.card h4:hover {
  color: #ff4612;
  transition: 0.5s;
}
</style>
