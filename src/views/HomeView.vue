<template>
  <div class="home">
    <AppHeader :products="computedproduct" @addproduct="addProductToCart" />
    <IntroSection />

    <ShopCart
      :products="computedproduct"
      :isCartOpen="computedisCartOpen"
      @removeitemToCart="removeitemToCart"
      @update:cartOpen="updateCartOPen"
      class="shop-cart"
    ></ShopCart>

    <AppProducts
      subheading="Discover our sun protection products"
      @addproduct="addProductToCart"
    />

    <SkinBanner />
    <AppEucerin />
    <MedicineBanner />

    <AppMeasure />
    <AppNewsLetter />
    <ParentComponent />
    <AppMap title="The Eucerin pharmacy near you" />
    <AppFooter />
  </div>
</template>

<script>
import AppHeader from "../components/layout/AppHeader";

import IntroSection from "../components/IntroSection.vue";

import ShopCart from "../components/ShopCart.vue";

import AppProducts from "../components/AppProducts.vue";
import SkinBanner from "../components/SkinBanner.vue";
import AppEucerin from "../components/AppEucerin.vue";
import MedicineBanner from "../components/MedicineBanner.vue";
import AppMeasure from "../components/AppMeasure.vue";
import AppNewsLetter from "../components/AppNewsLetter.vue";
import ParentComponent from "../components/emit/ParentComponent.vue";
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
    ParentComponent,
    AppMap,
    AppFooter,
  },
  data() {
    return {
      product: [],
      cartOpen: false,
    };
  },
  methods: {
    addProductToCart(newProduct) {
      this.cartOpen = true;
      this.product.push(newProduct);
    },
    removeitemToCart(product) {
      this.product.splice(this.product.indexOf(product));
    },
    updateCartOPen(close) {
      this.cartOpen = close;
    },
  },
  computed: {
    computedproduct() {
      return this.product;
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
