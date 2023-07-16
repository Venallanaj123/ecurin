<template>
  <div>
    <HeaderDesktop :lengthCart="products.length" class="header-desktop" />
    <HeaderMobile class="header-mobile" />
  </div>
</template>

<script>
import HeaderDesktop from "./HeaderDesktop.vue";
import HeaderMobile from "./HeaderMobile.vue";

export default {
  name: "AppHeader",
  components: { HeaderDesktop, HeaderMobile },
  props: ["products"],
};
</script>
<style scoped lang="scss">
@media only screen and (max-width: 768px) {
  .header-desktop {
    display: none;
  }
}
@media only screen and (min-width: 769px) {
  .header-mobile {
    display: none;
  }
}
</style>
