<template>
    <section class="map">
        <div class="map__container container">
            <div class="row">
                <div class="col span_2_of_2">
                    <h2 class="map__title">{{ title }}</h2>
                </div>
            </div>
            <div class="row">
                <div class="col span_2_of_2">

                    <div class="map__search">
                        <input type="text" class="map__input" placeholder="Search..." />
                        <span class="map__input--icon fas fa-search"> </span>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script>
export default {
    name: "AppMap",
    props: {
        title: {
            type: String,
            required: true,
        },
    },
    mounted() {
        // Initialize map here
    },
};
</script>

<style lang="scss" scoped>
@import "../assets/scss/grid/grid";

.map {
    background-image: url("../assets/images/maps/maps.jpg");
    /*height: 50%;*/
    height: 500px;
    background-position: center;
    background-repeat: no-repeat;
    position: relative;
    background-size: cover;

    &__container {}

    &__title {
        @include heading;
        padding-top: 10rem;
        font-size: 2.4rem;
        line-height: 2.9rem;
        text-align: center;
    }

    &__search {
        position: relative;
        display: flex;
        justify-content: center;
        align-items: center;
    }

    &__input {
        font-size: 16px;
        padding: 13px 45px 13px 14px;
        border-radius: 5px;
        border: none;
        box-shadow: 0 0 5px rgba(0, 0, 0, 0.3);
        margin-right: 10px;

        &--icon {
            background-image: url("../assets/images/search-svg.svg");
            background-repeat: no-repeat;
            background-position: left;
            cursor: pointer;
            position: absolute;

            right: 550px;
            fill: #7a858d;
            height: 20px;
            width: 20px;
            padding: 16px;
        }
    }
}

@media only screen and (max-width: 768px) {
    .map {
        &__input {

            &--icon {
                right: 250px;
            }
        }

    }
}
</style>
