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
          <span>mentorship</span>
          <span>78%</span>
        </div>
        <div class="education">
          <span>education</span>
          <span>95%</span>
        </div>
        <div class="learning">
          <span>learning</span>
          <span>65%</span>
        </div>
        <div class="motivation">
          <span>motivation</span>
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
}
.right {
  width: 50%;
  padding: 20px;
}
.mentorship,
.education,
.learning,
.motivation {
  display: flex;
  justify-content: space-between;
}
</style>
