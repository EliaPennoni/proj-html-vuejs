<script>
import SpecialtiesSections from "./MainSections/Specialties.Sections.vue";
import JasonBickford from "./MainSections/JasonBickford.vue";
import UpcomingEvent from "./MainSections/UpcomingEvent.vue";
import CreativeLeader from "./MainSections/CreativeLeader.vue";
export default {
  data() {
    return {};
  },
  components: {
    SpecialtiesSections,
    JasonBickford,
    UpcomingEvent,
    CreativeLeader,
  },
};
</script>

<template>
  <SpecialtiesSections />

  <JasonBickford />

  <UpcomingEvent />

  <CreativeLeader />
</template>

<style lang="scss">
@use "/src/assets/scss/general.scss" as *;
</style>
