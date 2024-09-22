<script>
import SpecialtiesSections from "./MainSections/Specialties.Sections.vue";
import JasonBickford from "./MainSections/JasonBickford.vue";
import UpcomingEvent from "./MainSections/UpcomingEvent.vue";
import CreativeLeader from "./MainSections/CreativeLeader.vue";
import LatestNews from "./MainSections/LatestNews.vue";
import Testimonials from "./MainSections/Testimonials.vue";
import Picture from "./MainSections/Picture.vue";
export default {
  data() {
    return {};
  },
  components: {
    SpecialtiesSections,
    JasonBickford,
    UpcomingEvent,
    CreativeLeader,
    LatestNews,
    Testimonials,
    Picture,
  },
};
</script>

<template>
  <SpecialtiesSections />

  <JasonBickford />

  <UpcomingEvent />

  <CreativeLeader />

  <latestNews />

  <Testimonials />

  <Picture />
</template>

<style lang="scss">
@use "/src/assets/scss/general.scss" as *;
</style>
