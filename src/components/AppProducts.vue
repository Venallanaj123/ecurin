<template>
  <section class="products">
    <div class="products__container container">
      <AppTitle
        title="Discover our sun protection products
                                                "
      />

      <hr class="hr" />
      <div class="row">
        <div
          class="col span_1_of_4 span_1_of_2 col-sm"
          v-for="card in cards"
          :key="card.id"
        >
          <a :href="card.href">
            <div class="product__card card">
              <div class="card__image">
                <img :src="card.img" alt="card-image" />
              </div>

              <div class="card__body">
                <div class="total-stars-review">
                  <ul class="stars" data-rating-value="4.5">
                    <li class="full-star">
                      <img src="../assets/images/star-svg.svg" alt="" />
                    </li>
                    <li class="full-star">
                      <img src="../assets/images/star-svg.svg" alt="" />
                    </li>
                    <li class="full-star">
                      <img src="../assets/images/star-svg.svg" alt="" />
                    </li>
                    <li class="full-star">
                      <img src="../assets/images/star-svg.svg" alt="" />
                    </li>
                    <li class="full-star">
                      <img src="../assets/images/star-svg.svg" alt="" />
                    </li>
                  </ul>
                  <span class="total-reviews-count">• 120</span>
                </div>
                <p class="card__title">{{ card.title }}</p>
                <p class="card__subtile">{{ card.subtitle }}</p>
              </div>
            </div>
          </a>
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
      cards: [
        {
          id: 1,
          href: "https://www.eucerin.de/produkte/sonnenschutz/sun-face-hydro-protect-ultra-light-50plus",
          img: "https://i.postimg.cc/vDRKZSRp/hydro-protect.png",
          title: "sun protection",
          subtitle: "Hydro Protect Ultra Light Face Sun Fluid   ",
        },
        {
          id: 2,
          href: "https://www.eucerin.de/produkte/sun-protection/oil-control-face-sun-gel-creme-lsf-50-plus",
          img: "https://i.postimg.cc/4NQC3sdP/oil-control.png",
          title: "sun protection",
          subtitle: "Hydro Protect Ultra Light Face Sun Fluid   ",
        },
        {
          id: 3,
          href: "https://www.eucerin.de/produkte/sonnenschutz/oil-control-body-sun-gel-creme-dry-touch-lsf-50plus",
          img: "https://i.postimg.cc/0yXB6QqY/dry-touch.png",
          title: "sun protection",
          subtitle: "Hydro Protect Ultra Light Face Sun Fluid  ",
        },
        {
          id: 4,
          href: "https://www.eucerin.de/produkte/sun-protection/allergy-protection-after-sun-creme-gel",
          img: "https://i.postimg.cc/x1BPDb24/crem-gel.png",
          title: "sun protection",
          subtitle: "Hydro Protect Ultra Light Face Sun Fluid  ",
        },
      ],
    };
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import "../assets/scss/grid/grid";

.products {
  a {
    text-decoration: none;

    & .product__card {
      @include card;

      & .card__image {
        & img {
          width: 100%;
          height: auto;
          object-fit: cover;
        }
      }

      & .card__body {
        padding: 2.5rem 1.5rem;

        & .total-stars-review {
          display: flex;
          position: relative;
          align-items: center;

          & ul {
            display: flex;
            align-items: center;
            justify-content: flex-start;

            & li {
              list-style: none;

              & img {
                width: 1.5rem;
                height: 1.5rem;
              }
            }
          }

          & span {
            color: #4e5c67;
            font-size: 1rem;
            line-height: 1.2rem;
            padding-left: 2rem;
          }
        }

        & .card__title {
          @include card-title;
        }

        & .card__subtile {
          @include card-subtitle;
        }
      }

      &:hover {
        box-shadow: 0 8px 16px 0 rgba(0, 0, 0, 0.2);
      }
    }
  }
}

/*@media only screen and (max-width: $breakpoint-xsm) {
    .row {
        flex-direction: column;
    }

    .products {
        &__subheading {
            & h2 {
                font-size: 20px;
                margin: 15px 0;
            }
        }

        .product__card {
            padding: 0 !important;
            margin: 10px 0 !important;
        }
    }
}*/

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
