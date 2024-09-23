<script>
export default {
  data() {},
  methods: {},
};
</script>

<template>
  <div class="background">
    <div class="circles">
      <div class="first">
        <h3>12</h3>
        <span>Years of Experience</span>
      </div>
      <div class="second">
        <h3>36</h3>
        <span>Successful Projects</span>
      </div>
      <div class="third">
        <h3>76</h3>
        <span>Reliable Clients</span>
      </div>
      <div class="fourth">
        <h3>12</h3>
        <span>Years of Experience</span>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@use "/src/assets/scss/general.scss" as *;
.background {
  color: white;
}
.circles {
  width: 80%;
  height: 600px;
  margin: 0 auto;
  display: flex;
  align-items: center;
  justify-content: space-evenly;
}
.first,
.second,
.third,
.fourth {
  background-color: #ff4612;
  color: white;
  text-align: center;
  font-family: "Libre Baskerville", serif;
  width: 200px; /* Larghezza uguale all'altezza per un cerchio perfetto */
  height: 200px; /* Altezza uguale alla larghezza */
  display: flex;
  flex-direction: column;
  justify-content: center; /* Centra verticalmente */
  align-items: center; /* Centra orizzontalmente */
  border-radius: 50%; /* Fa sì che l'elemento diventi un cerchio */
  position: relative;
}
.first h3,
.second h3,
.third h3,
.fourth h3 {
  background-color: #ff4612;
  color: white;
  text-align: center;
  font-family: "Libre Baskerville", serif;
  font-size: 55px;
  font-weight: 600;
}
.first span::after,
.second span::after,
.third span::after,
.fourth span::after {
  content: "";
  display: inline-block;
  width: 60px;
  height: 2px;
  background-color: white;
  position: absolute;
  bottom: 30px;
  right: 35%;
}
</style>
