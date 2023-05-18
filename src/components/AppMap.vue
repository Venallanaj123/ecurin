<template>
  <section class="map">
    <div class="map__container container">
      <div class="row">
        <div class="col span_2_of_2">
          <AppTitle title="The Eucerin pharmacy near you" />
        </div>
      </div>
      <div class="row">
        <div class="col span_2_of_2">
          <div class="map__search">
            <input
              type="text"
              class="map__input"
              placeholder=" City or Zip code .."
            />
            <span class="map__input--icon"> </span>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import AppTitle from "./AppTitle";
export default {
  name: "AppMap",
  components: { AppTitle },
  props: {
    title: {
      type: String,
      required: true,
    },
  },
};
</script>

<style lang="scss" scoped>
@import "../assets/scss/grid/grid";

.map {
  background-image: url("../assets/images/maps/maps.jpg");
  height: 500px;
  background-position: center;
  background-repeat: no-repeat;
  position: relative;
  background-size: cover;

  &__title {
    @include subheading;
  }

  &__search {
    position: relative;
    display: flex;
    justify-content: center;
    align-items: center;
  }

  &__input {
    font-size: 1.6rem;
    line-height: 2.4rem;
    padding: 13px 45px 13px 14px;
    border-radius: 5px;
    border: none;
    box-shadow: 0 0 5px rgba(0, 0, 0, 0.3);
    margin-right: 10px;
    font-style: italic;
    width: 25%;

    &--icon {
      background-image: url("../assets/images/search-svg.svg");
      background-repeat: no-repeat;
      background-position: left;
      cursor: pointer;
      position: absolute;
      right: 550px;
      height: 20px;
      width: 20px;
      padding: 16px;
    }
  }
}

@media only screen and (max-width: 425px) {
  .map {
    &__input {
      width: 80% !important;
      &--icon {
        right: 70px !important;
      }
    }
  }
}
@media only screen and (max-width: 768px) {
  .map {
    &__input {
      width: 40%;
      &--icon {
        right: 250px;
      }
    }
  }
}
</style>
