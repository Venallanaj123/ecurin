<template>
  <div>
    <AppHeaderDesktop :lengthCart="products.length" class="header-desktop" />
    <AppHeaderMobile class="header-mobile" />
  </div>
</template>

<script>
import AppHeaderDesktop from "./AppHeaderDesktop.vue";
import AppHeaderMobile from "./AppHeaderMobile.vue";

export default {
  name: "AppHeader",
  components: { AppHeaderDesktop, AppHeaderMobile },
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
