<script>
export default {
  data() {},
  methods: {},
};
</script>

<template>
  <div class="background">
    <img src="/public/teach/img/h1-img-04.jpg" alt="" />
    <i class="fa-solid fa-play fa-2x"></i>
  </div>
</template>

<style lang="scss" scoped>
@use "/src/assets/scss/general.scss" as *;
.background {
  position: relative;
}
.background img {
  width: 100%;
}
.background i {
  position: absolute;
  top: 50%;
  left: 50%;
  color: white;
  cursor: pointer;
}
.background i:hover {
  color: lightgray;
  opacity: 3;
  font-size: xx-large;
}
</style>
