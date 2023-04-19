<template>
    <AppHeader />
    <IntroSection />
    <AppProducts subheading="Discover our sun protection products" />

    <SkinBanner />
    <AppEucerin subheading="Discover Eucerin
                                                    " />
    <MedicineBanner subheading="Discover our measures" />


    <AppMeasure />
    <AppNewsLetter />

    <AppFooter />

    <router-view />
</template>

<script>
// @ is an alias to /src
import AppHeader from './components/layout/AppHeader.vue';

import IntroSection from './components/IntroSection.vue'
import AppProducts from './components/AppProducts.vue'
import SkinBanner from './components/SkinBanner.vue'
import AppEucerin from './components/AppEucerin.vue';

import MedicineBanner from './components/MedicineBanner.vue';
import AppMeasure from './components/AppMeasure.vue'
import AppNewsLetter from './components/AppNewsLetter.vue'

import AppFooter from './components/layout/AppFooter.vue';


export default {
    name: 'App',
    components: {
        AppHeader,

        IntroSection,
        AppProducts,
        SkinBanner,
        AppEucerin,
        MedicineBanner,
        AppMeasure,
        AppNewsLetter,
        /*IntroSection,
        SkinBanner,
       ,*/
        AppFooter
    }
}
</script>
<style lang="scss"></style>
