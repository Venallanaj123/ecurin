<template>
  <section class="products">
    <div class="products__container container">
      <AppTitle
        title="Discover our sun protection products
"
      />

      <hr class="hr" />
      <div class="row">
        <div class="col-3" v-for="card in cards" :key="card.id">
          <a :href="card.href">
            <div class="product__card card">
              <div class="card__image">
                <img :src="card.img" alt="card-image" />
              </div>

              <div class="card__body">
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
  & .hr {
    @include hr;
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

        & .card__title {
          text-transform: uppercase;
          color: $grey-light;
          margin: 0.5rem 0;
        }

        & .card__subtile {
          color: $grey-light;
          margin: 0.5rem 0;
        }
      }

      &:hover {
        box-shadow: 0 8px 16px 0 rgba(0, 0, 0, 0.2);
      }
    }
  }
}

@media only screen and (max-width: $breakpoint-xsm) {
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
}
</style>
