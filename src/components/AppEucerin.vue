<template>
    <section class="eucerin">


        <div class="eucerin__container container">

            <div class="eucerin__row row">
                <div class=" eucerin__col-subheading col-12">
                    <div class="eucerin__subheading ">
                        <h2 class=" eucerin__subheading subheading">{{ subheading }}</h2>

                    </div>


                </div>

            </div>
            <div class="row">
                <div class="col-12">
                    <div class="eucerin__hr--bottom"></div>
                </div>
            </div>
            <div class="row">
                <div class="eucerin__card card" v-for=" card in cards" :key="card.id">
                    <img src="../assets/images/eucerin/eucerin.jpg" alt=" euceri" class="card__img">
                    <div class="card__body">
                        <p class="card__title">{{ card.title }}</p>
                        <p class="card__subtile"> {{ card.subtitle }}</p>
                    </div>

                </div>
            </div>
            <div class="row">
                <div class="col-12">
                    <div class="eucerin__button">
                        <a href="https://www.eucerin.de/produkte/sonnenschutz" class="eucerin__button--btn-grey">Find sun
                            protection eucerin</a>
                    </div>
                </div>

            </div>
        </div>
    </section>
</template>

<script>
export default {
    name: 'AppEucerin',
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


                    title: "sun protection",
                    subtitle: "Hydro Protect Ultra Light Face Sun Fluid   ",
                },
                {
                    id: 2,
                    title: "sun protection",
                    subtitle: "Hydro Protect Ultra Light Face Sun Fluid   ",
                },
                {
                    id: 3,
                    title: "sun protection",
                    subtitle: "Hydro Protect Ultra Light Face Sun Fluid  ",
                },
                {
                    id: 3,
                    title: "sun protection",
                    subtitle: "Hydro Protect Ultra Light Face Sun Fluid  ",
                },

            ]
        }
    }
}
</script>
<style scoped lang="scss">
@import "../assets/scss/grid/grid";

.eucerin {

    &__subheading {
        & h2 {
            @include subheading;
        }

    }

    .eucerin {
        &__hr--bottom {
            border-bottom: 1px solid $border-color;
            margin-bottom: 18px;
            padding-bottom: 6px;
        }
    }

    .eucerin__card {
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


.eucerin__card:hover {
    box-shadow: 0 8px 16px 0 rgba(0, 0, 0, 0.2);
}

@media only screen and (max-width: $breakpoint-xsm) {
    .row {
        flex-direction: column;
    }

    .eucerin {

        &__subheading {
            & h2 {

                font-size: 20px;
                margin: 15px 0;
            }

        }

        .eucerin__card {
            padding: 0 !important;
            margin: 10px 0 !important;
        }


    }
}
</style>