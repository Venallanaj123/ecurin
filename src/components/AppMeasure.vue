<template>
    <section class="measur">


        <div class="measur__container container">

            <div class="measur__row row">
                <div class=" measur__col-subheading col-12">
                    <div class="measur__subheading ">
                        <h2 class=" measur__subheading subheading">{{ subheading }}</h2>

                    </div>



                </div>

            </div>
            <div class="row">
                <div class="col-12">
                    <div class="measur__hr--bottom"></div>
                </div>
            </div>
            <div class="row">
                <div class="measur__card card" v-for=" card in cards" :key="card.id">
                    <img src="../assets/images/measures/euc-teaser.jpg" alt=" hydro-protect" class="card__img">
                    <div class="card__body">
                        <p class="card__title">{{ card.title }}</p>
                        <p class="card__subtile"> {{ card.subtitle }}</p>
                        <p class="card__time">{{ card.time }}</p>
                    </div>

                </div>
            </div>
            <div class="row">
                <div class="col-12">
                    <div class="measur__button">
                        <a href="https://www.eucerin.de/produkte/sonnenschutz" class="measur__button--btn-grey">Find sun
                            protection measur</a>
                    </div>
                </div>

            </div>
        </div>
    </section>
</template>

<script>
export default {
    name: 'AppMeasure',
    props: {
        subheading: String
    },
    components: {

    },
    data: function () {
        return {
            cards: [
                {
                    id: 1,


                    title: "Sustainable production and sourcing",
                    subtitle: "Building a sustainable supply chain   ",
                    time: "4 min reading time"
                },
                {
                    id: 2,
                    title: "Sustainable production and sourcing",
                    subtitle: "Building a sustainable supply chain   ",
                    time: "4 min reading time"
                },
                {
                    id: 3,
                    title: "Sustainable production and sourcing",
                    subtitle: "Building a sustainable supply chain   ",
                    time: "3 min reading time"
                },
                {
                    id: 3,
                    title: "Sustainable production and sourcing",
                    subtitle: "Building a sustainable supply chain   ",
                    time: "6 min reading time"
                },

            ]
        }
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import "../assets/scss/grid/grid";

.measur {

    &__subheading {
        & h2 {
            @include subheading;
        }

    }

    .measur {
        &__hr--bottom {
            border-bottom: 1px solid $border-color;
            margin-bottom: 18px;
            padding-bottom: 6px;
        }
    }

    .measur__card {
        @include card;

        & img {
            width: 100%;
            height: auto;
            object-fit: cover;
        }

        .card__body {
            padding: 20px;

            & .card__title {
                text-transform: uppercase;
                color: $grey-light;
                font-size: 12px;
                margin: 5px 0;
            }

            & .card__subtile {
                color: $grey-light;
                font-size: 16px;
                margin: 5px 0;
            }
        }

    }

    &__button {
        display: flex;
        justify-content: center;
        align-items: center;
        margin: 20px 0;


        &--btn-grey {
            @include btngrey;
        }

        &--btn-grey:hover {
            background-color: $grey-btnhover;
        }


    }
}


.measur__card:hover {
    box-shadow: 0 8px 16px 0 rgba(0, 0, 0, 0.2);
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

        .measur__card {
            padding: 0 !important;
            margin: 10px 0 !important;
        }


    }
}
</style>
