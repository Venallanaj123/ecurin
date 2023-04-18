<template>
    <AppHeader />
    <IntroSection />
    <SkinBanner />
    <MedicineBanner />
    <DiscoverMeasure />
    <!-- <AppTest /> -->
    <AppFooter />

    <router-view />
</template>

<script>
// @ is an alias to /src
import AppHeader from './components/layout/AppHeader.vue';
import AppTest from './components/AppTest.vue'
import IntroSection from './components/IntroSection.vue'
import SkinBanner from './components/SkinBanner.vue'

import MedicineBanner from './components/MedicineBanner.vue';
import DiscoverMeasure from './components/DiscoverMeasure.vue'
// import AppTest from './components/AppTest.vue'
import AppFooter from './components/layout/AppFooter.vue';


export default {
    name: 'App',
    components: {
        AppHeader,
        AppTest,
        IntroSection,
        SkinBanner,
        MedicineBanner,
        DiscoverMeasure,
        /*IntroSection,
        SkinBanner,
        AppTest,*/
        AppFooter
    }
}
</script>
<style lang="scss"></style>
