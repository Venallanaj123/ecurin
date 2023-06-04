<template>
  <section class="product-detail">
    <div class="container">
      <div class="row">
        <div class="col span_1_of_2">
          <div class="product-detail__carousel">
            <div class="product-detail__stage">
              <div class="product-detail__image">
                <Carousel
                  id="gallery-carousel"
                  :itemsToShow="1"
                  :wrap-around="false"
                  v-model="currentSlide"
                  @slideChange="onSlideChange"
                  ref="carousel"
                >
                  <Slide v-for="(image, index) in images" :key="index">
                    <div class="gallery__item">
                      <img :src="image.src" />
                    </div>
                  </Slide>
                  <Navigation slot="navigation" />
                </Carousel>
              </div>
            </div>
            <div class="product-detail__thumbnails">
              <Carousel
                :settings="settings"
                :breakpoints="breakpoints"
                id="thumbnail-carousel"
                :itemsToShow="7"
                :wrap-around="true"
                v-model="currentSlide"
                ref="carousel"
              >
                <Slide v-for="(image, index) in images" :key="index">
                  <div class="product-detail__thumbnail">
                    <img
                      :src="image.thumbnailSrc"
                      @click="selectImage(index)"
                    />
                  </div>
                </Slide>
              </Carousel>
            </div>
          </div>
        </div>
        <div
          class="col span_1_of_2"
          v-for="(product, index) in products"
          :key="index"
        >
          <div class="product-detail__description">
          
            <div
              class="star-rating"
              v-for="(review, index) in stars"
              :key="index"
            >
              <i
                v-for="(star, index) in review.star"
                :key="index"
                class="star-rating__star fa fa-star checked"
                style="color: orange"
              ></i>
              <span>{{ review.comment }}</span>
            </div>

            <h1 class="product-detail__title">
              {{ product.title }}
            </h1>
            <p class="product-detail__quantity">
              {{ product.quantity }}
            </p>

            <div class="product-detail__price">
              <div class="product-detail__price--wraper">
                <span class="price"> {{ product.price }}</span>
                <i
                  class="fas fa-info-circle"
                  @mouseenter="showTooltip = true"
                  @mouseleave="showTooltip = false"
                ></i>
                <span class="tooltip" v-if="showTooltip">
                  <h3>{{ product.heading }}</h3>
                  <p class="content">{{ product.content }}</p>
                </span>
              </div>
            </div>
            <p class="product-detail__discount">
              {{ product.discount }}
            </p>
            <select v-model="selectedOption" class="product-detail__seclect">
              <option value="">1</option>
              <option
                v-for="(option, index) in options"
                :key="index"
                :value="option.value"
              >
                {{ option.label }}
              </option>
            </select>

            <p class="product-detail__feedback">
              {{ product.availability }}
            </p>

            <button class="product-detail__button">In den Warenkorb</button>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import { defineComponent } from "vue";
import { Carousel, Slide, Navigation } from "vue3-carousel";
import "vue3-carousel/dist/carousel.css";

export default defineComponent({
  props: {
    title: String,
    text: String,
    star: Number,
    comment: String,
  },
  name: "TestSlider",
  components: { Carousel, Slide, Navigation },

  data: () => ({
    currentSlide: 0,
    images: [
      {
        id: 1,
        src: require("../../assets/images/nivea/nive-1.jpg"),
        thumbnailSrc: require("../../assets/images/nivea/nive-1.jpg"),
      },
      {
        id: 2,
        src: require("../../assets/images/nivea/nive-2.jpg"),
        thumbnailSrc: require("../../assets/images/nivea/nive-2.jpg"),
      },
      {
        id: 3,
        src: require("../../assets/images/nivea/nive-3.jpg"),
        thumbnailSrc: require("../../assets/images/nivea/nive-3.jpg"),
      },
      {
        id: 4,
        src: require("../../assets/images/nivea/nive-4.jpg"),
        thumbnailSrc: require("../../assets/images/nivea/nive-4.jpg"),
      },
      {
        id: 5,
        src: require("../../assets/images/nivea/nive-5.jpg"),
        thumbnailSrc: require("../../assets/images/nivea/nive-5.jpg"),
      },
      {
        id: 6,
        src: require("../../assets/images/nivea/nive-6.jpg"),
        thumbnailSrc: require("../../assets/images/nivea/nive-6.jpg"),
      },
      {
        id: 7,
        src: require("../../assets/images/nivea/nive-7.jpg"),
        thumbnailSrc: require("../../assets/images/nivea/nive-7.jpg"),
      },
    ],

    products: [
      {
        title: "schutzund pflege sonnenspray ",
        quantity: " Lichtschutzfaktor 30  |  200 ml",
        price: "10,72 €",
        heading: "Notice",
        content: "Incl. 19.00% VAT plus 3.95 €  shipping costs",
        href: "shipping costs",
        discount: "1  |  53,60 €",
        availability: " Sofort lieferbar",

        buttonText: "In den Warenkorb",
      },
    ],

    selectedOption: "",
    options: [
      { label: " 2", value: "2" },
      { label: " 3", value: "3" },
      { label: " 4", value: "4" },
    ],

    items: [
      {
        text: "Enter your comment here",
      },
    ],
    stars: [
      {
        star: 5,
        comment: "(10)",
      },
    ],
    // settings: {
    //   itemsToShow: 1,
    //   snapAlign: "center",
    // },

    // breakpoints: {

    //   700: {
    //     itemsToShow: 4,
    //     snapAlign: "center",
    //   },

    //   1024: {
    //     itemsToShow: 7,
    //     snapAlign: "start",
    //   },
    // },
  }),

  methods: {
    selectImage(index) {
      this.currentSlide = index;
    },

    onSlideChange() {},
  },
});
</script>

<style lang="scss" scoped>
.star-rating {
  display: inline-block;
}

.star-rating__star {
  font-size: 2rem;
  color: grey;
}

.checked {
  color: orange;
}
.product-detail__rating {
  padding: 10px;
  margin-bottom: 20px;
}

.star-rating__star {
  font-size: 24px;
  color: orange;
  cursor: pointer;
}
.star {
  font-size: 24px !important;
  color: orange !important;
  cursor: pointer;
}

@import "../../assets/scss/component/nivea";
@import "../../assets/scss/grid/grid";
.stars {
  font-size: 0;
}
</style>
