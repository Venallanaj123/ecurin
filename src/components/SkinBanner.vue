<template>
    <section class="skin-banner">
        <div class="container">
            <div class="row">
                <div class="col-6">
                    <div class="skin-banner__content">
                        <h2 class="skin-banner__content--heading">Our sunny present for you
                        </h2>
                        <p class="skin-banner__content--text">€3 discount on Eucerin Sun products
                        </p>
                        <button class="skin-banner__content__button--primary">Find skin care now</button>
                    </div>
                </div>
                <div class="col-6">

                </div>
            </div>


        </div>

    </section>
</template>

<script>
export default {
    name: "SkinBanner",

};
</script>

<style scoped lang="scss">
@import "../assets/scss/abstracts/mixins";
@import "../assets/scss/grid/grid";

.skin-banner {
    background-image: url("../assets/images/skinbanner.jpg");
    height: 500px;
    background-position: center;
    background-repeat: no-repeat;

    position: relative;

    &__content {
        width: 100%;
        padding-top: 100px;
        padding-bottom: 50px;

        &--heading {
            margin-bottom: 5px;
            font-size: 3.5rem;
            line-height: 4rem;
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



/* Extra small devices (phones, 600px and down) */
@media only screen and (max-width: 600px) {
    .skin-banner {


        background-size: cover;
        height: 100%;
        width: 100%;
        max-height: 100%;

    }
}
</style>
