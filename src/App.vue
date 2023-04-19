<template>
    <AppHeader />
    <IntroSection />
    <AppProducts subheading="Discover our sun protection products
        " />
    <SkinBanner />
    <MedicineBanner />
    <DiscoverMeasure />

    <AppFooter />

    <router-view />
</template>

<script>
// @ is an alias to /src
import AppHeader from './components/layout/AppHeader.vue';

import IntroSection from './components/IntroSection.vue'
import AppProducts from './components/AppProducts.vue'
import SkinBanner from './components/SkinBanner.vue'

import MedicineBanner from './components/MedicineBanner.vue';
import DiscoverMeasure from './components/DiscoverMeasure.vue'

import AppFooter from './components/layout/AppFooter.vue';


export default {
    name: 'App',
    components: {
        AppHeader,

        IntroSection,
        AppProducts,
        SkinBanner,
        MedicineBanner,
        DiscoverMeasure,
        /*IntroSection,
        SkinBanner,
       ,*/
        AppFooter
    }
}
</script>
<style lang="scss"></style>
