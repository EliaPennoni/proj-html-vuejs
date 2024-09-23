<script>
import SpecialtiesSections from "./MainSections/Specialties.Sections.vue";
import JasonBickford from "./MainSections/JasonBickford.vue";
import UpcomingEvent from "./MainSections/UpcomingEvent.vue";
import CreativeLeader from "./MainSections/CreativeLeader.vue";
import LatestNews from "./MainSections/LatestNews.vue";
import Testimonials from "./MainSections/Testimonials.vue";
import Picture from "./MainSections/Picture.vue";
import OrangeCircles from "./MainSections/OrangeCircles.vue";
import Teachers from "./MainSections/Teachers.vue";
import ContactUs from "./MainSections/ContactUs.vue";
import PricingPlan from "./MainSections/PricingPlan.vue";
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
    OrangeCircles,
    Teachers,
    ContactUs,
    PricingPlan,
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

  <OrangeCircles />

  <Teachers />

  <ContactUs />

  <PricingPlan />
</template>

<style lang="scss">
@use "/src/assets/scss/general.scss" as *;
</style>
