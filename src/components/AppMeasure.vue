<template>
  <section class="measur">
    <div class="measur__container container">
      <AppTitle title="Discover our measures" />
      "
      <div class="row">
        <div class="col span_1_of_4" v-for="card in cards" :key="card.id">
          <a :href="card.href">
            <div class="card">
              <div class="card__image">
                <img :src="card.img" alt="card-image" />
              </div>

              <div class="card__content">
                <p class="card__title">{{ card.title }}</p>
                <p class="card__subtile">{{ card.subtitle }}</p>
                <p class="card__time">{{ card.time }}</p>
              </div>
            </div>
          </a>
        </div>
      </div>

      <div class="measur__btn">
        <a href="https://www.eucerin.de/produkte/sonnenschutz"
          >Discover our sustainability approach</a
        >
      </div>
    </div>
  </section>
</template>

<script>
import AppTitle from "./AppTitle.vue";
import AppButton from "./AppButton.vue";

export default {
  name: "Appmeasur",
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
          href: "https://www.eucerin.de/nachhaltigkeit/co2-reduzierung/nachhaltige-produktion",
          img: require("../assets/images/measures/euc-teaser.png"),
          title: "Sustainable production and sourcingn",
          subtitle: "Building a sustainable supply chain",
          time: " 4 min reading time",
        },
        {
          id: 2,
          href: "https://www.eucerin.de/nachhaltigkeit/co2-reduzierung/klimaschutz",
          img: require("../assets/images/measures/ecurin-envairment.png"),
          title: "Climate protection at Eucerin",
          subtitle: "Climate protection at Eucerin ",
          time: "3 min reading time",
        },
        {
          id: 3,
          href: "https://www.eucerin.de/nachhaltigkeit/co2-reduzierung/nachhaltige-verpackung",
          img: require("../assets/images/measures/bottles.png"),
          title: "Sustainable packaging at Eucerin",
          subtitle: "Sustainable packaging at Eucerin  ",
          time: " 5 min reading time",
        },
        {
          id: 4,
          href: "https://www.eucerin.de/nachhaltigkeit/hochwertige-inhaltsstoffe/nachhaltiger-palmoel-anbau",
          img: require("../assets/images/measures/palmoil-teaser.png"),
          title: "Raw materials in skin care",
          subtitle: "Sustainable sourcing of palm oil",
          time: " 7 min reading time",
        },
      ],
    };
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import "../assets/scss/grid/grid";

.measur {
  background-color: $grey;

  .center-title {
    @include subheading;
    text-align: center;
  }

  a {
    text-decoration: none;

    & .card {
      @include card;

      &__image {
        & img {
          width: 100%;
          height: auto;
        }
      }

      &__content {
        padding: 2.5rem 1.5rem;

        &__title {
          text-transform: uppercase;
          margin-bottom: 4px;
          font-size: 1.2rem;
          line-height: 2rem;
          max-height: 18px;
          color: #767676;
          font-weight: 600;
        }

        &__subtile {
          color: $grey-light;
          margin: 0.5rem 0;
          font-size: 1.6rem;
          line-height: 2.4rem;
        }

        &__time {
          font-size: 1.4rem;
          line-height: 2rem;
        }
      }

      &:hover {
        box-shadow: 0 8px 16px 0 rgba(0, 0, 0, 0.2);
      }
    }
  }

  &__btn {
    display: flex;
    justify-content: center;
    margin: 2rem 0;

    & a {
      background-color: #fff;
      font-size: 1.6rem;
      line-height: 2.4rem;
      font-weight: bold;
      padding: 1.5rem 6rem;
      cursor: pointer;
      color: $black-light;
      text-decoration: none;
    }
  }
}

.card__title {
  text-transform: uppercase;
  margin-bottom: 4px;
  font-size: 1.2rem;
  line-height: 2rem;

  color: #767676;
  font-weight: 600;
  font-family: "EucerinaWgl-Demibold";
}
.card__subtile {
  color: $grey-light;
  margin: 0.5rem 0;
  font-size: 1.6rem;
  line-height: 2rem;
  margin-bottom: 4px;
}
@media only screen and (max-width: 768px) {
  .measur__btn > a {
    padding: 1.5rem 4rem;
  }
}
</style>
