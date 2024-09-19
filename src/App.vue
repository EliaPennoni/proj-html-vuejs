<script>
import AppHeader from "./components/AppHeader.vue";

export default {
  components: {
    AppHeader,
  },
};
</script>

<template>
  <div>
    <AppHeader />
  </div>
</template>

<style lang="scss" scoped>
@use "/src/assets/scss/general.scss" as *;

h1 {
  color: red;
}
</style>



