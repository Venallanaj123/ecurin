<template>
  <section class="intro-section">
    <div class="container">
      <div class="row">
        <div class="col-8">
          <div class="intro-section__element">
            <h1 class="intro-section__element--heading">
              Our sunny present for you
            </h1>
            <p class="intro-section__element--text">
              €3 discount on Eucerin Sun products
            </p>
            <button class="intro-section__button--primary">
              Find participating pharmacies
            </button>
          </div>
        </div>
        <div class="col-4"></div>
      </div>
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
@import "../assets/scss/abstracts/variables";

.intro-section {
  background-image: url("../assets/images/intro-section-background.jpg");
  height: 500px;
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
  position: relative;

  &__element {
    width: 100%;
    padding: 10rem 0;

    &--heading {
      @include heading;
      font-size: 4.4rem;
      font-weight: inherit;
      line-height: 4.8rem;
    }

    &--text {
      @include text;
    }

    & button {
      @include button;
    }

    & button:hover {
      background-color: $danger-dark;
    }
  }
}

@media only screen and (max-width: 768px) {
  .intro-section {
    // width: 100%;
    // height: 100%;
  }
}
</style>
