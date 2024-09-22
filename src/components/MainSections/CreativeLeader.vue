<script>
export default {
  data() {},
  methods: {},
};
</script>

<template>
  <div class="background">
    <div class="container">
      <div class="left">
        <h3>Creative Leader</h3>
        <p>
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Sit,
          provident. At nam accusantium ad sapiente facere minima cumque, vel
          sed?
        </p>
        <span>Read More</span>
      </div>
      <div class="right">
        <div class="mentorship">
          <span>Mentorship</span>
          <span>78%</span>
        </div>
        <div class="education">
          <span>Education</span>
          <span>95%</span>
        </div>
        <div class="learning">
          <span>Learning</span>
          <span>65%</span>
        </div>
        <div class="motivation">
          <span>Motivation</span>
          <span>83%</span>
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@use "/src/assets/scss/general.scss" as *;
.background {
  background-color: white;
  width: 100%;
}
.container {
  width: 80%;
  margin: 0 auto;
  padding: 20px;
  display: flex;
}
.left {
  width: 50%;
  padding: 20px;
  position: relative;
}
.left h3 {
  font-size: 35px;
  font-family: "Libre Baskerville", serif;
  margin-bottom: 40px;
}
.left p {
  margin-bottom: 20px;
  margin-top: 20px;
  color: gray;
}
.left h3::after {
  content: "";
  display: inline-block;
  width: 5px;
  height: 5px;
  background-color: #ff4612;
  border-radius: 50%;
  margin-left: 3px;
  vertical-align: baseline;
}
.left p::after {
  content: "";
  display: inline-block;
  width: 60px;
  height: 2px;
  background-color: #ff4612;
  position: absolute;
  bottom: 140px;
  left: 20px;
}
.left span {
  font-weight: bold;
}
.left span::before {
  content: "\f178";
  font-family: "Font Awesome 5 Free";
  font-weight: 900;
  position: absolute;
  left: 0px;
  bottom: 10px;
  transform: translateY(-50%);
  opacity: 0;
  transition: opacity 0.5s ease, left 0.5s ease;
}

.left span:hover::before {
  opacity: 1;
}

.right {
  width: 50%;
  padding: 30px;
}
.mentorship,
.education,
.learning,
.motivation {
  display: flex;
  justify-content: space-between;
  font-family: "Libre Baskerville", serif;
  font-size: 19px;
  font-weight: 600;
  position: relative;
  margin-bottom: 30px;
}
.mentorship::before,
.education::before,
.learning::before,
.motivation::before {
  content: "";
  display: inline-block;
  width: 100%; /* Barra grigia è larga quanto il contenitore */
  height: 3px;
  background-color: lightgray;
  position: absolute;
  bottom: -10px;
  left: 0;
}

/* Barra arancione (usa ::after) */
.mentorship::after,
.education::after,
.learning::after,
.motivation::after {
  content: "";
  display: inline-block;
  height: 3px;
  background-color: #ff4612;
  position: absolute;
  bottom: -10px;
  left: 0;
}

.mentorship::after {
  width: 78%; /* Percentuale di completamento per mentorship */
}

.education::after {
  width: 95%; /* Percentuale di completamento per education */
}

.learning::after {
  width: 65%; /* Percentuale di completamento per learning */
}

.motivation::after {
  width: 83%; /* Percentuale di completamento per motivation */
}
</style>
