<template>
  <section class="intro-section intro-section-mobile">
    <div class="container">
      <div class="row">
        <div class="col span_1_of_2">
          <div class="intro-section__element">
            <h1 class="intro-section__element--heading">
              Our sunny present for you
            </h1>
            <p class="intro-section__element--text">
              €3 discount on Eucerin Sun products
            </p>
            <a
              href="https://www.eucerin.de/#layer=pharmacy-finder.rabattaktion_sonnenschutz"
              class="intro-section__element--button"
            >
              Find participating pharmacies
            </a>
          </div>
        </div>
        <div class="col span_1_of_2"></div>
      </div>
      <!-- <div class="row">
        <div class="col span_2_of_2">
          <div class="intro-section__elementmobile">
            <h1 class="intro-section__element--heading">
              Our sunny present for you
            </h1>
            <p class="intro-section__element--text">
              €3 discount on Eucerin Sun products
            </p>
            <a
              href="https://www.eucerin.de/#layer=pharmacy-finder.rabattaktion_sonnenschutz"
              class="intro-section__element--button"
            >
              Find participating pharmacies
            </a>
          </div>
        </div>
      </div> -->
    </div>
  </section>
</template>

<script>
export default {
  name: "IntroSection",
};
</script>

<style scoped lang="scss">
@import "../assets/scss/grid/grid";
h1 {
  color: black;
}
.intro-section {
  background-image: url("../assets/images/intro-section-background.jpg");
  height: 500px;
  background-size: cover;
  background-position: center;
  position: relative;

  &__element {
    @include left;

    &--heading {
      @include heading;
      font-size: 4.4rem;

      line-height: 5rem;
      margin-bottom: 1.5rem;
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

@media only screen and (max-width: 768px) {
  .intro-section-mobile {
    background-image: url("../assets/images/intro-section-backgroundmobile.jpg");
    height: auto;
    min-height: 100vh;
    background-size: cover;
    background-position: center;
  }
  .intro-section__element {
    top: 120%;
    &--heading {
      font-size: 2.8rem;

      margin-bottom: 0;
    }
    &--text {
      margin-bottom: 1rem;
    }
  }
}
</style>
