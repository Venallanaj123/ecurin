<template>
  <section class="product-detail">
    <div class="container">
      <div class="row">
        <div class="col span_1_of_2">
          <div class="product-detail__carousel">
            <div class="product-detail__stage">
              <div
                class="product-detail__image"
                @wheel.prevent="handleWheelScroll"
              >
                <img :src="images[activeImage].full" alt="image" />
              </div>
              <!-- <div class="product-detail__actions">
                <span @click="prevImage" class="prev">
                  <i class="fas fa-chevron-left"></i>
                </span>
                <span @click="nextImage" class="next">
                  <i class="fas fa-chevron-right"></i>
                </span>
              </div> -->
            </div>
            <div class="product-detail__thumbnails">
              <div
                v-for="(image, index) in images"
                :key="image.id"
                :class="[
                  'thumbnail-image',
                  activeImage == index ? 'active' : '',
                ]"
                @click="activateImage(index)"
              >
                <img :src="image.thumb" />
                <!-- <div class="thumbnail-number">
                  {{ index + 1 }}/{{ totalImages }}
                </div> -->
              </div>
            </div>
          </div>
        </div>
        <div
          class="col span_1_of_2"
          v-for="(product, index) in products"
          :key="index"
        >
          <div class="product-detail__description">
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
      <div class="hr"></div>
    </div>
  </section>
</template>

<script>
export default {
  name: "AppNivea",
  data() {
    return {
      showTooltip: false,
      activeImage: 0,
      //   totalImages: 5,

      images: [
        {
          id: 1,
          thumb: require("../../assets/images/nivea/nive-1.jpg"),
          full: require("../../assets/images/nivea/nive-1.jpg"),
        },
        {
          id: 2,
          thumb: require("../../assets/images/nivea/nive-2.jpg"),
          full: require("../../assets/images/nivea/nive-2.jpg"),
        },
        {
          id: 3,
          thumb: require("../../assets/images/nivea/nive-3.jpg"),
          full: require("../../assets/images/nivea/nive-3.jpg"),
        },
        {
          id: 4,
          thumb: require("../../assets/images/nivea/nive-4.jpg"),
          full: require("../../assets/images/nivea/nive-4.jpg"),
        },
        {
          id: 5,
          thumb: require("../../assets/images/nivea/nive-5.jpg"),
          full: require("../../assets/images/nivea/nive-5.jpg"),
        },
        {
          id: 6,
          thumb: require("../../assets/images/nivea/nive-6.jpg"),
          full: require("../../assets/images/nivea/nive-6.jpg"),
        },
        {
          id: 7,
          thumb: require("../../assets/images/nivea/nive-7.jpg"),
          full: require("../../assets/images/nivea/nive-7.jpg"),
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
    };
  },

  mounted() {
    this.totalImages = this.images.length;
  },
  methods: {
    nextImage() {
      this.activeImage =
        this.activeImage < this.totalImages - 1 ? this.activeImage + 1 : 0;
    },
    prevImage() {
      this.activeImage =
        this.activeImage > 0 ? this.activeImage - 1 : this.totalImages - 1;
    },
    activateImage(index) {
      this.activeImage = index;
    },
  },
};
</script>

<style lang="scss" scoped>
@import "../../assets/scss/grid/grid";
$basecolor: #0032a0;

.container {
  max-width: 1200px;
  margin: 0 auto;
}
.row {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.product-detail {
  display: flex;
  justify-content: space-between;
  align-items: center;

  &__description {
    text-align: center;
    margin-top: -170px;
  }
  &__title {
    color: $basecolor;
    text-transform: uppercase;
    margin-top: 0;
    font-size: 3.6rem;
    line-height: 5.4rem;
    margin-bottom: 10px;
    font-weight: bold;
  }
  &__quantity {
    color: $basecolor;
    margin-bottom: 10px;
    font-size: 1.8rem;
    line-height: 2.7rem;
  }
  &__price {
    margin-bottom: 10px;
    display: flex;
    align-items: center;
    justify-content: center;
  }
  &__price--wraper {
  }
  & span {
    color: $basecolor;
    font-weight: bold;
    margin-bottom: 10px;
    font-size: 1.8rem;
    line-height: 2.1rem;
  }
  & .fas {
    margin-left: 10px;
    font-size: 15px;
  }
  /* & .tooltip {
    position: absolute;
    top: 100%;
    width: 70%;
    height: auto;
    left: 50%;
    transform: translateX(-50%);
    padding: 10px 20px;
    background-color: #eff5fa;
    border: 1px solid #d6dcec;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.12);
    z-index: 999;
    display: none;
    margin-left: -30px;
    border-radius: 3px;
  }*/
  &__discount {
    color: $basecolor;
    font-weight: normal;
    margin-bottom: 10px;
    font-size: 1.8rem;
    line-height: 2.1rem;
  }
  &__seclect {
    background-color: #f5f5f5;
    border: none;
    color: $basecolor;

    width: 60px;
    padding: 2px 16px 2px 8px;
    font-size: 16px;
    cursor: pointer;
    border-radius: 8px;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.2);
    margin-bottom: 10px;
  }
  &__feedback {
    color: $basecolor;
    margin-bottom: 10px;
    display: flex;
    align-items: center;
    justify-content: center;
  }
  &__feedback::before {
    content: "";
    background-color: #64a70b;
    border-radius: 50%;
    content: "";
    display: inline-block;
    height: 10px;
    margin-right: 4px;
    width: 10px;
  }
  &__button {
    background-color: #ff8c00;
    color: white;
    border: none;
    cursor: pointer;
    width: 40%;
    font-size: 1.6rem;
    border-radius: 50px;
    height: 55px;
    hyphens: auto;
    line-height: 1.2rem;
    outline: none;
    overflow: hidden;
    padding: 4px 24px;
    text-decoration: none;
    text-transform: uppercase;
    white-space: normal;
    font-weight: 600;
  }
  &__button:hover {
    background-color: orange;
  }

  &__carousel {
    position: relative;
  }
  &__stage {
    background-color: #c6ccda;
    box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
    width: 70%;
    margin: 0 auto;
  }
  &__image {
    height: 100%;
    position: relative;
    width: auto;
    display: flex;
    align-items: center;
    justify-content: center;
    margin-bottom: 30px;
  }
  &__image::before {
    content: "";
    background-color: #c6ccda;
    position: absolute;
    height: calc(100% - 20%);
    width: 150%;
    top: 0;
  }
  img {
    height: auto;
    max-height: 100%;
    max-width: 100%;
    position: relative;
    width: auto;
  }
  &__actions {
  }
  &__thumbnails {
    display: flex;
    align-items: center;
    align-items: center;
    margin-top: 30px;
  }
  & .thumbnail-image {
    /* margin: 0 5px;
    cursor: pointer;
    transition: opacity 0.2s ease-in-out;*/

    margin: 0 5px;
    cursor: pointer;
    transition: opacity 0.2s ease-in-out;
    display: flex;
    align-items: center;
    align-items: center;
    background-color: white;

    border: 1px solid #d6dcec;
    height: 70px;
    justify-content: center;
    padding: 3px;
    position: relative;
    width: 70px;
  }
  & .thumbnail-image img {
    height: 100%;
  }
  & .thumbnail-image.active {
    opacity: 0.5;
    border-bottom: 3px solid #0032a0;
  }
  .hr {
    display: block;
    margin: 30px 0;
    border: 0;
    border-bottom: 1px solid $border-color;
    height: 1px;
  }
}
</style>
