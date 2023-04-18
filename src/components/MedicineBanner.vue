<template>
    <section class="medicine-banner">
        <div class="container">
            <div class="row">
                <div class="col-6">
                    <div class="medicine-banner__element">
                        <h2 class="medicine-banner__element--heading">Our sustainability approach
                        </h2>
                        <p class="medicine-banner__element--text">Measures and goals at Eucerin
                        </p>
                        <button class="medicine-banner__button--primary">Learn more</button>


                    </div>
                </div>
                <div class="col-6"></div>

            </div>
        </div>


    </section>
</template>

<script>
export default {
    name: 'MedicineBanner',
    props: {
        msg: String
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import "../assets/scss/grid/grid";

.medicine-banner {
    background-image: url("../assets/images/banner-3.jpg");
    /*height: 50%;*/
    background-position: center;
    background-repeat: no-repeat;
    position: relative;
    height: 440px;

    &__element {
        width: 100%;
        padding-top: 100px;
        padding-bottom: 50px;

        &--heading {
            color: $white;
            font-size: 36px;
            margin-bottom: 5px;
            line-height: 40px;
        }

        &--text {
            margin-bottom: 20px;
            color: $grey-light;
            font-size: 1.2rem;
            line-height: 24px;

        }

        & button {
            @include button;
            padding: 7px 50px;

        }

        & button:hover {
            background-color: $danger-dark;
        }
    }
}

@media only screen and (max-width: 768px) {
    .medicine-banner {
        height: 100%;
        width: 100%;
        background-size: cover;
        /* background-size: contain;*/

        &__element {
            width: 100%;
            padding-top: 100px;
            padding-bottom: 50px;

            &--heading {
                font-size: 3rem;
                font-weight: bold;
                margin-bottom: 10px;

            }
        }
    }

}
</style>
