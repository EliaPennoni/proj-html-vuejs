<script>
import SpecialtiesSections from "./MainSections/Specialties.Sections.vue";
import JasonBickford from "./MainSections/JasonBickford.vue";
export default {
  data() {
    return {};
  },
  components: {
    SpecialtiesSections,
    JasonBickford,
  },
};
</script>

<template>
  <SpecialtiesSections />

  <JasonBickford />
</template>

<style lang="scss">
@use "/src/assets/scss/general.scss" as *;
</style>
