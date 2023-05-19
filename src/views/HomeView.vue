<template>
  <div class="home">
    <AppHeader />
    <IntroSection />

    <AppProducts subheading="Discover our sun protection products" />

    <!-- <SkinBanner /> -->
    <AppEucerin />
    <!-- <MedicineBanner /> -->

    <AppMeasure />
    <!-- <AppNewsLetter /> -->

    <!-- <AppMap title="The Eucerin pharmacy near you" /> -->
    <AppFooter />
  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'
import AppHeader from "../components/layout/AppHeader";

import IntroSection from "../components/IntroSection.vue";
import AppProducts from "../components/AppProducts.vue";
// import SkinBanner from "./components/SkinBanner.vue";
import AppEucerin from "../components/AppEucerin.vue";
// import MedicineBanner from "./components/MedicineBanner.vue";
import AppMeasure from "../components/AppMeasure.vue";
// import AppNewsLetter from "./components/AppNewsLetter.vue";
// import AppMap from "./components/AppMap.vue";
import AppFooter from "../components/layout/AppFooter";

export default {
  name: "HomeView",
  components: {
    AppHeader,
    IntroSection,

    AppProducts,
    // SkinBanner,
    AppEucerin,
    // MedicineBanner,
    AppMeasure,
    // AppNewsLetter,
    // AppMap,
    AppFooter,
  },
};
</script>
