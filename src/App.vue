<template>
  <div id="app">
    <!-- <AppHeader /> 
    <AppNested />-->

    <AppHeaderMobile />

    <IntroSection />
    <AppProducts subheading="Discover our sun protection products" />

    <SkinBanner />
    <AppEucerin />
    <MedicineBanner />

    <AppMeasure />
    <AppNewsLetter />

    <AppMap title="The Eucerin pharmacy near you" />
    <AppFooter />
    <router-view />
  </div>
</template>

<script>
// // @ is an alias to /src
//  import AppHeader from "./components/layout/AppHeader.vue";
// import AppNestedVue from "./components/layout/AppNested.vue";

import AppHeaderMobile from "./components/layout/AppHeaderMobile.vue";
import IntroSection from "./components/IntroSection.vue";
import AppProducts from "./components/AppProducts.vue";
import SkinBanner from "./components/SkinBanner.vue";
import AppEucerin from "./components/AppEucerin.vue";
import MedicineBanner from "./components/MedicineBanner.vue";
import AppMeasure from "./components/AppMeasure.vue";
import AppNewsLetter from "./components/AppNewsLetter.vue";
import AppMap from "./components/AppMap.vue";
import AppFooter from "./components/layout/AppFooter.vue";

export default {
  name: "App",
  components: {
    AppHeaderMobile,
    //AppHeader,
    // AppHeaderMobile,
    //AppNestedVue,
    IntroSection,
    AppProducts,
    SkinBanner,
    AppEucerin,
    MedicineBanner,
    AppMeasure,
    AppNewsLetter,
    AppMap,
    AppFooter,
  },
};
</script>
<style lang="scss">
@import "../src/assets/scss/base/global";
</style>
