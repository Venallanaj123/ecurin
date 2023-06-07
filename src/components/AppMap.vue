<template>
  <section class="map">
    <div class="container">
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
            <span class="map__input--icon">
              <svg
                class="cp-pharmacy_location-icon"
                width="25px"
                height="25px"
                version="1.1"
                id="Capa_1"
                xmlns="http://www.w3.org/2000/svg"
                xmlns:xlink="http://www.w3.org/1999/xlink"
                x="0px"
                y="0px"
                viewBox="0 0 477.883 477.883"
                style="enable-background: new 0 0 477.883 477.883"
                xml:space="preserve"
              >
                <g>
                  <g>
                    <path
                      d="M468.456,1.808c-4.811-2.411-10.478-2.411-15.289,0l0,0L9.433,223.675c-8.429,4.219-11.842,14.471-7.624,22.9
			                            c2.401,4.798,6.919,8.188,12.197,9.151l176.111,32.034l32.034,176.111c1.311,7.219,7.091,12.793,14.353,13.841
			                            c0.803,0.116,1.613,0.173,2.423,0.171c6.469,0.003,12.383-3.651,15.275-9.438L476.07,24.711
			                            C480.292,16.284,476.883,6.03,468.456,1.808z M246.557,407.38l-24.986-137.353c-1.292-6.936-6.718-12.362-13.653-13.653
			                            L70.498,231.32L422.634,55.244L246.557,407.38z"
                    ></path>
                  </g>
                </g>
              </svg>
            </span>
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
    width: 100%;
    max-width: 335px;
    z-index: 1001;
    display: flex;
    align-items: center;
    justify-content: center;
    margin: 0 auto;
  }

  &__input {
    font-family: "Roboto-Regular";
    font-size: 1.8rem;
    line-height: 2.6rem;
    background-color: #fff;
    border: 1px solid #e8eaeb;
    border-radius: 4px;
    box-shadow: 0 2px 10px 0 rgba(0, 0, 0, 0.2);
    color: #a7adb3;
    padding: 13px 45px 13px 14px;
    letter-spacing: normal;
    font-style: italic;
    outline: none;
    width: inherit;

    &--icon {
      cursor: pointer;
      position: absolute;
      top: 50%;
      -webkit-transform: translateY(-50%);
      transform: translateY(-50%);
      right: 15px;
      fill: #7a858d;
      height: 25px;
      width: 25px;
    }
  }
}
</style>
