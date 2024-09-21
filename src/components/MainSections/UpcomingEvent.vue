<script>
export default {
  data() {},
  methods: {},
};
</script>

<template>
  <div class="background">
    <div class="container">
      <div>
        <h3>Upcoming Events</h3>
      </div>
      <p>Sorry, no posts matched your criteria.</p>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@use "/src/assets/scss/general.scss" as *;
.background {
  background-color: #fafafa;
  width: 100%;
}
.container {
  background-color: #fafafa;
  width: 80%;
  margin: 0 auto;
  padding: 20px;
}
.container div {
  height: 100px;
  width: 500px;
  background-color: white;
  box-shadow: 2px 3px 10px 0 rgba(0, 0, 0, 0.09);
}

.container div h3 {
  padding: 30px;
  font-size: 30px;
  font-family: "Libre Baskerville", serif;
}
.container p {
  margin-top: 10px;
  color: gray;
}
</style>
