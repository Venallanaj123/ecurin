<template>
    <section class="measur ">
        <div class="measur__container container">
            <AppTitle title="Discover our measures

                                                                                      " />


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
                                <p class="card__time">{{ card.time }}</p>
                            </div>
                        </div>
                    </a>
                </div>
            </div>
            <div class="measur__btn">
                <a href="https://www.eucerin.de/produkte/sonnenschutz">Discover our sustainability approach</a>
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
                    title: "sun protection",
                    subtitle: "Hydro Protect Ultra Light Face Sun Fluid   ",
                    time: " 4 min reading time",
                },
                {
                    id: 2,
                    href: "https://www.eucerin.de/nachhaltigkeit/co2-reduzierung/klimaschutz",
                    img: require("../assets/images/measures/ecurin-envairment.png"),
                    title: "sun protection",
                    subtitle: "Hydro Protect Ultra Light Face Sun Fluid   ",
                    time: "3 min reading time",
                },
                {
                    id: 3,
                    href: "https://www.eucerin.de/nachhaltigkeit/co2-reduzierung/nachhaltige-verpackung",
                    img: require("../assets/images/measures/bottles.png"),
                    title: "sun protection",
                    subtitle: "Hydro Protect Ultra Light Face Sun Fluid  ",
                    time: " 5 min reading time",
                },
                {
                    id: 4,
                    href: "https://www.eucerin.de/nachhaltigkeit/hochwertige-inhaltsstoffe/nachhaltiger-palmoel-anbau",
                    img: require("../assets/images/measures/palmoil-teaser.png"),
                    title: "sun protection",
                    subtitle: "Hydro Protect Ultra Light Face Sun Fluid  ",
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

    & .hr {
        @include hr;
    }

    .center-title {
        @include heading;
        text-align: center;


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

                & .card__time {
                    font-size: 1.4rem;
                    margin-top: 2rem ;
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
            font-size: 1.3rem;
            line-height: 1.5rem;
            font-weight: bold;
            padding: 1.2rem 3rem;
            cursor: pointer;
            border: none;
            text-align: center;
            color: $black-light;
            text-decoration: none;
            transition: all 0.3s ease;
            display: inline-block;
        }
    }


}

.btn-center {

    &__global {
        @include btngrey;
        background-color: #fff !important;

        &:hover {
            background-color: $grey-btnhover;
        }
    }
}

@media only screen and (max-width: $breakpoint-xsm) {
    .row {
        flex-direction: column;
    }

    .measur {
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
