<template>
    <section class="products">


        <div class="products__container container">

            <div class="products__row row">
                <div class=" products__col-subheading col-12">
                    <div class="products__subheading ">
                        <h2 class=" products__subheading subheading">{{ subheading }}</h2>

                    </div>


                </div>

            </div>
            <div class="row">
                <div class="col-12">
                    <div class="products__hr--bottom"></div>
                </div>
            </div>
            <div class="row">
                <div class="product__card card" v-for=" card in cards" :key="card.id">
                    <img src="../assets/images/products/hydro-protect.jpg" alt=" hydro-protect" class="card__img">
                    <div class="card__body">
                        <p class="card__title">{{ card.title }}</p>
                        <p class="card__subtile"> {{ card.subtitle }}</p>
                    </div>

                </div>
            </div>
            <div class="row">
                <div class="col-12">
                    <div class="products__button">
                        <a href="https://www.eucerin.de/produkte/sonnenschutz" class="products__button--btn-grey">Find sun
                            protection product</a>
                    </div>
                </div>

            </div>
        </div>
    </section>
</template>

<script>
export default {
    name: 'AppProducts',
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

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import "../assets/scss/grid/grid";

.products {

    &__subheading {
        & h2 {
            @include subheading;
        }

    }

    .products {
        &__hr--bottom {
            border-bottom: 1px solid $border-color;
            margin-bottom: 18px;
            padding-bottom: 6px;
        }
    }

    .product__card {
        box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
        transition: 0.3s;
        width: 100%;
        padding: 20px 5px;
        margin: 10px;
        height: 100%;
        cursor: pointer;

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


.product__card:hover {
    box-shadow: 0 8px 16px 0 rgba(0, 0, 0, 0.2);
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
