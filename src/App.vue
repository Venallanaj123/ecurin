<template>
  <div id="app">
    <AppHeader />
    <!-- <AppTest /> -->
    <IntroSection />

    <SkinBanner />
    <MedicineBanner />

    <!-- <AppHeader />
    <IntroSection />
  <AppProducts subheading="Discover our sun protection products" />

    <SkinBanner />
    <AppEucerin
      subheading="Discover Eucerin
                                                                                "
    />
    <MedicineBanner subheading="Discover our measures" />

    <AppMeasure />
    <AppNewsLetter />
    <AppMap subheading="Die Eucerin Apotheke in deiner Nähe" />-->

    <AppMap title="The Eucerin pharmacy near you" />
    <AppFooter />
    <router-view />
  </div>
</template>

<script>
// @ is an alias to /src
import AppHeader from "./components/layout/AppHeader.vue";
//import IntroSection from "./components/IntroSection.vue";
// import AppTest from "./components/AppTest.vue";
import IntroSection from "./components/IntroSection.vue";

// import IntroSection from './components/IntroSection.vue'
// import AppProducts from './components/AppProducts.vue'
import SkinBanner from "./components/SkinBanner.vue";
// import AppEucerin from './components/AppEucerin.vue';

import MedicineBanner from "./components/MedicineBanner.vue";
// import AppMeasure from './components/AppMeasure.vue'
// import AppNewsLetter from './components/AppNewsLetter.vue'
import AppMap from "./components/AppMap.vue";
import AppFooter from "./components/layout/AppFooter.vue";

export default {
  name: "App",
  components: {
    AppHeader,
    IntroSection,
    SkinBanner,
    MedicineBanner,
    AppMap,
    AppFooter,
  },
};
</script>
<style lang="scss">
@import "../src/assets/scss/base/global";
</style>
