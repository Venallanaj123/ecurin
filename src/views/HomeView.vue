<template>
  <div class="home">
    <AppHeader />
    <IntroSection />

    <ShopCart
      :products="computedProductInfo"
      :isCartOpen="computedisCartOpen"
      v-on:removeitemToCart="removeitemToCart"
      class="shop-cart"
    ></ShopCart>

    <AppProducts
      subheading="Discover our sun protection products"
      :productInfo="productInfo"
      :cartOpen="cartOpen"
      @update:productInfo="updateProductInfo"
    />

    <SkinBanner />
    <AppEucerin />
    <MedicineBanner />

    <AppMeasure />
    <AppNewsLetter />

    <AppMap title="The Eucerin pharmacy near you" />
    <AppFooter />
  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'
import AppHeader from "../components/layout/AppHeader";

import IntroSection from "../components/IntroSection.vue";

import ShopCart from "../components/ShopCart.vue";

import AppProducts from "../components/AppProducts.vue";
import SkinBanner from "../components/SkinBanner.vue";
import AppEucerin from "../components/AppEucerin.vue";
import MedicineBanner from "../components/MedicineBanner.vue";
import AppMeasure from "../components/AppMeasure.vue";
import AppNewsLetter from "../components/AppNewsLetter.vue";
import AppMap from "../components/AppMap.vue";
import AppFooter from "../components/layout/AppFooter";

export default {
  name: "HomeView",
  components: {
    AppHeader,
    IntroSection,

    ShopCart,
    AppProducts,
    SkinBanner,
    AppEucerin,
    MedicineBanner,
    AppMeasure,
    AppNewsLetter,
    AppMap,
    AppFooter,
  },
  data() {
    return {
      productInfo: [],
      cartOpen: false,
    };
  },
  methods: {
    updateProductInfo(newProduct) {

      this.cartOpen = true;
      this.productInfo.push(newProduct);
    },

    removeitemToCart(product) {
      this.productInfo.splice(this.productInfo.indexOf(product));
    },
  },
  computed: {
    computedProductInfo() {
      return this.productInfo;
    },
    computedisCartOpen() {
      return this.cartOpen;
    },
  },
};
</script>
<style scoped>
.shop-cart {
  visibility: hidden;
}
</style>
