<template>
  <section class="skin-banner">
    <div class="container">
      <div class="row">
        <div class="col span_1_of_2">
          <div class="skin-banner__content">
            <h2 class="skin-banner__content--heading">
              Our sunny present for you
            </h2>
            <p class="skin-banner__content--text">
              €3 discount on Eucerin Sun products
            </p>
            <a
              href="https://www.eucerin.de/meta-pages/produktfinder"
              class="skin-banner__content--button"
            >
              Find skin care now</a
            >
          </div>
        </div>
        <div class="col span_1_of_2"></div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "SkinBanner",
};
</script>

<style scoped lang="scss">
@import "../assets/scss/abstracts/mixins";
@import "../assets/scss/grid/grid";

.skin-banner {
  background-image: url("../assets/images/skinbanner.jpg");
  height: 500px;
  background-position: center;
  background-repeat: no-repeat;

  position: relative;

  &__content {
    width: 100%;
    padding-top: 100px;
    padding-bottom: 50px;

    &--heading {
      @include heading;
    }

    &--text {
      @include text;
    }

    &--button {
      @include button;
    }

    &--button:hover {
      background-color: $danger-dark;
    }
  }
}

/* Extra small devices (phones, 600px and down) */
@media only screen and (max-width: 600px) {
  .skin-banner {
    background-size: cover;
    height: 100%;
    width: 100%;
    max-height: 100%;
  }
}
</style>
