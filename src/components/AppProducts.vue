<template>
    <section class="products">
      <div class="container">
        <AppTitle title=" Discover our sun protection products " />
  
        <hr class="hr" />
        <div class="row">
          <div
            class="col span_1_of_4 span_1_of_2 col-sm"
            v-for="(product, index) in products"
            :key="index"
          >
            <!-- <a class="products__link" :href="product.href"> </a> -->
            <div class="product">
              <div class="product__image">
                <img :src="product.img" alt="product-image" />
              </div>
  
              <div class="product__info">
                <div
                  class="product__rating"
                  v-for="(review, index) in stars"
                  :key="index"
                >
                  <i
                    v-for="(star, index) in review.star"
                    :key="index"
                    class="product__star fa fa-star checked"
                  ></i>
                  <span class="product__comment">{{ review.comment }}</span>
                </div>
  
                <p class="product__title">{{ product.title }}</p>
                <p class="product__subtile">{{ product.subtitle }}</p>
  
                <div class="product__cart">
                  <div class="product__price">
                    <p class="product__price-regular">
                      {{ product.price }}
                    </p>
                    <p class="product__price-volume">
                      {{ product.volume }}
                    </p>
                  </div>
  
                  <button @click="additemToCart(product)" class="product__button">
                    <svg
                      width="28"
                      height="28"
                      viewBox="0 0 32 32"
                      fill="none"
                      xmlns="http://www.w3.org/2000/svg"
                    >
                      <path
                        d="M8.72723 10.1818H23.2727L25.4545 28H6.54541L8.72723 10.1818Z"
                        stroke="white"
                      ></path>
                      <path
                        d="M20.3636 10.1818C20.3636 10.1818 20.3636 8.51 20.3636 7.99999C20.3636 5.59002 18.41 3.63635 16 3.63635C13.59 3.63635 11.6364 5.59002 11.6364 7.99999C11.6364 8.51 11.6364 10.1818 11.6364 10.1818"
                        stroke="white"
                      ></path>
                      <path d="M11.6364 19.6364H20.3636" stroke="white"></path>
                      <path d="M16 15.2727V24" stroke="white"></path>
                    </svg>
                  </button>
                </div>
              </div>
            </div>
          </div>
        </div>
        <AppButton
          link="https://www.eucerin.de/produkte/sonnenschutz"
          buttonText="Find sun protection product"
        />
      </div>
    </section>
  </template>
  
  <script>
  import AppTitle from "./AppTitle.vue";
  import AppButton from "./AppButton.vue";
  
  export default {
    name: "AppProducts",
    props: {
      link: {
        type: String,
        required: true,
      },
    },
    components: {
      AppTitle,
      AppButton,
    },
    data: function () {
      return {
        products: [
          {
            id: 1,
            href: "https://www.eucerin.de/produkte/sonnenschutz/sun-face-hydro-protect-ultra-light-50plus",
            img: require("../assets/images/products/hydro-protect.png"),
            title: "sun protection",
            subtitle: "Hydro Protect Ultra Light Face Sun Fluid   ",
            price: "€11.49",
            volume: "1 PC | 1pc = €11.49",
          },
          {
            id: 2,
            href: "https://www.eucerin.de/produkte/sun-protection/oil-control-face-sun-gel-creme-lsf-50-plus",
            img: require("../assets/images/products/dry-touch.png"),
            title: "sun protection",
            subtitle: "Hydro Protect Ultra Light Face Sun Fluid   ",
            price: "€42.49",
            volume: "30 ml | 1 l = € 1,416.33",
          },
          {
            id: 3,
            href: "https://www.eucerin.de/produkte/sonnenschutz/oil-control-body-sun-gel-creme-dry-touch-lsf-50plus",
            img: require("../assets/images/products/oil-control.png"),
            title: "sun protection",
            subtitle: "Hydro Protect Ultra Light Face Sun Fluid  ",
            price: "€24.99",
            volume: "5 ml | 1 l = € 1,4,998.00",
          },
          {
            id: 4,
            href: "https://www.eucerin.de/produkte/sun-protection/allergy-protection-after-sun-creme-gel",
            img: require("../assets/images/products/crem-gel.png"),
            title: "sun protection",
            subtitle: "Hydro Protect Ultra Light Face Sun Fluid  ",
            price: "€34.49",
            volume: "30 ml | 1 l = € 1,149.67",
          },
        ],
        stars: [
          {
            star: 5,
            comment: "5.0",
          },
        ],
      };
    },
    methods: {
      additemToCart(product) {
        this.$emit("update:productInfo", product);
      },
    },
  };
  </script>
  
  <!-- Add "scoped" attribute to limit CSS to this component only -->
  
  <style lang="scss" scoped>
  @import "../assets/scss/grid/grid";
  
  .products {
    &__link {
      text-decoration: none;
    }
  }
  
  .product {
    @include card;
  
    &__image {
    }
  
    img {
      width: 100%;
      height: 100%;
      object-fit: cover;
    }
  
    &__info {
      flex: 1;
      padding: 2.5rem 1.5rem;
    }
  
    &__rating {
      display: flex;
      align-items: center;
    }
  
    &__star {
      color: black;
    }
  
    &__comment {
      color: #223341;
      font-size: 1rem;
      line-height: 1.2rem;
      padding-left: 1rem;
      font-weight: bold;
    }
  
    &__title {
      @include card-title;
    }
  
    &__subtile {
      @include card-subtitle;
    }
  
    &:hover {
      outline: 1px solid #cfcfcf;
    }
  
    &__cart {
      -webkit-box-align: center;
      align-items: center;
      display: flex;
      -webkit-box-orient: horizontal;
      -webkit-box-direction: reverse;
      flex-direction: row-reverse;
      -webkit-box-pack: end;
      justify-content: flex-end;
      gap: 8px;
      margin-top: 12px;
    }
  
    &__button {
      background-color: #a70532;
      cursor: pointer;
      width: 40px;
      height: 40px;
      border-radius: 50%;
      -webkit-box-flex: 0;
      flex: 0 0 40px;
      border: none;
      position: relative;
    }
  
    svg {
      position: absolute;
      transform: translateX(-50%) translateY(-50%);
      left: 50%;
      top: calc(50% - 1px);
    }
  
    &__price {
      display: block;
  
      &-regular {
        font-weight: bold;
      }
  
      &-volume {
        color: #223341;
        font-size: 1.4rem;
        line-height: 1.8rem;
        margin-top: 2px;
        width: 100%;
        display: inline-block;
      }
    }
  }
  
  .product__button {
    svg {
      position: absolute;
      transform: translateX(-50%) translateY(-50%);
      left: 50%;
      top: calc(50% - 1px);
    }
  }
  
  @media screen and (max-width: 425px) {
    .span_1_of_2 {
      width: 49.2%;
      margin-bottom: 20px;
    }
  
    .col-sm {
      margin: 0;
    }
  }
  </style>
  