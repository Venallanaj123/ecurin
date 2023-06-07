<template>
  <section class="newsletter">
    <div class="container">
      <div class="row">
        <div class="col span_2_of_2" v-for="card in cards" :key="card.id">
          <div class="newsletter__wrap">
            <div class="newsletter__cards">
              <div class="newsletter__card">
                <div class="card__image">
                  <img :src="card.img" alt="card-image" />
                </div>

                <div class="card__body">
                  <h2 class="card__title">
                    Subscribe to Eucerin news <br />
                    and secure benefits
                  </h2>
                  <p
                    class="card__list"
                    v-for="(item, index) in items"
                    :key="index"
                  >
                    {{ item.name }}
                  </p>

                  <div class="card__button btn">
                    <a
                      href="https://www.eucerin.de/meta-pages/eucerin-newsletter-anmeldung"
                      >Subscribe to Newsletter</a
                    >
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "AppNewsLetter",
  props: {
    title: {
      type: String,
      required: true,
    },
  },
  data: function () {
    return {
      cards: [
        {
          id: 1,

          img: require("../assets/images/newsletter/newsletter.jpg"),
        },
      ],
      items: [
        { name: "• Test and evaluate new products", id: 1 },
        { name: "• Participate in attractive competitions ", id: 2 },
        { name: "• Receive up-to-date information and advice", id: 3 },
      ],
    };
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import "../assets/scss/grid/grid";

.newsletter {
  &__wrap {
    display: flex;
    align-items: center;
    justify-content: center;
  }

  &__cards {
    display: flex;
  }
  &__card {
    @include card;
    display: flex;
    justify-content: center;
    border: 1px solid #d2d5d8;
    border-radius: 5px;

    &__image {
    }
    img {
      width: 100%;
      max-width: 500px;
      height: auto;
    }

    & .card__body {
      padding: 2rem;

      & .card__title {
        font-size: 3.6rem;
        line-height: 4.4rem;
        color: $headingcolor;
        margin-bottom: 1.5rem;
        font-weight: 500;
      }

      & .card__list {
        margin: 1.2rem 0;
        font-size: 1.6rem;
        line-height: 1.9rem;
      }

      & .card__button {
        @include button;
        padding: 12px 35px;
        width: 100%;

        & a {
          color: #fff;
          text-decoration: none;
          font-size: 1.6rem;
          line-height: 1.9rem;
        }
      }
    }
  }
}

@media only screen and (max-width: 768px) {
  .newsletter {
    &__card {
      flex-direction: column;
    }
    &__title {
      font-size: 2.6rem;
      line-height: 3.4rem;
    }
  }
}
</style>
