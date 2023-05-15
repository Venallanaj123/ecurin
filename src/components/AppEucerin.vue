<template>
  <section class="eucerin">
    <div class="eucerin__container container">
      <AppTitle title="Discover Euceri" />

      <hr class="hr" />
      <div class="row">
        <div
          class="col span_1_of_4 span_1_of_2  test"
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
  name: "AppEucerin",
  props: {
    link: {
      type: String,
      required: true,
    },
    img: {
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
          href: "https://www.eucerin.de/produkte/hyaluron-filler/tagespflege",
          img: require("../assets/images/eucerin/eucerin.jpg"),
          title: "sun protection",
          subtitle: "Hydro Protect Ultra Light Face Sun Fluid   ",
        },
        {
          id: 2,
          href: "https://www.eucerin.de/produkte/anti-pigment/dual-serum",
          img: require("../assets/images/eucerin/anti-pigament.png"),
          title: "sun protection",
          subtitle: "Hydro Protect Ultra Light Face Sun Fluid   ",
        },
        {
          id: 3,
          href: "https://www.eucerin.de/produkte/dermo-pure/reinigungsgel",
          img: require("../assets/images/eucerin/dermopure.png"),

          title: "sun protection",
          subtitle: "Hydro Protect Ultra Light Face Sun Fluid  ",
        },
        {
          id: 4,
          href: "https://www.eucerin.de/produkte/urea-repair/plus-lotion-10prozent-urea",
          img: require("../assets/images/eucerin/urea-repair.png"),

          title: "sun protection",
          subtitle: "Hydro Protect Ultra Light Face Sun Fluid  ",
        },
      ],
    };
  },
};
</script>
<style scoped lang="scss">
@import "../assets/scss/grid/grid";

.eucerin {
  & .hr {
  }

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

@media screen and (max-width: 768px) {
  .test{
    width: 49.2%;
    margin-bottom: 20px;
  }
}


</style>
