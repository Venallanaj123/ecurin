<template>
    <section class="newsletter">
        <div class="container">
            <div class="row">
                <div class="col-12" v-for="card in cards" :key="card.id">
                    <div class="newsletter__card card">
                        <div class="card__image">

                            <img :src="card.img" alt="card-image" />
                        </div>

                        <div class="card__body">
                            <p class="card__title">{{ card.title }}</p>
                            <p class="card__list">{{ card.list1 }}</p>
                            <p class="card__list">{{ card.list2 }}</p>
                            <p class="card__list">{{ card.list3 }}</p>

                            <div class="card__button btn">
                                <a href="https://www.eucerin.de/meta-pages/eucerin-newsletter-anmeldung">Subscribe to
                                    Newsletter</a>
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
    name: 'AppNewsLetter',
    props: {
        title: {
            type: String,
            required: true
        },
    },
    data: function () {
        return {
            cards: [
                {
                    id: 1,

                    img: require("../assets/images/newsletter/newsletter.jpg"),
                    title: "Eucerin Neuigkeiten abonnieren und Vorteile sichern  ",
                    list1: "• Neue Produkte testen und bewerten",
                    list2: "• Neue Produkte testen und bewerten",
                    list3: "• Neue Produkte testen und bewerten",

                },

            ],
        };
    },

};

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import "../assets/scss/grid/grid";

.newsletter {


    &__card {
        @include card;
        display: flex;

        &__image {

            & img {
                width: 100%;
                max-width: 100%;
                height: auto;
            }
        }

        & .card__body {
            padding: 1rem;

            & .card__title {
                font-size: 3.6rem;
                line-height: 4.4rem;
                color: $headingcolor;
                margin-bottom: 1rem;
            }

            & .card__list {
                margin: 1rem 0;
                font-size: 1.6rem;
                line-height: 1.9rem
            }

            & .card__button {
                @include button;


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
    }
}
</style>
