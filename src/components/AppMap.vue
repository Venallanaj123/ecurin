<template>
    <section class="map">
        <div class="container">
            <div class="row">
                <div class="col-12">
                    <div class="map__subheading ">
                        <div class="grouping-element">
                            <h2 class=" map__subheading subheading">{{ subheading }}</h2>
                            <input type="text" id="myInput" placeholder="Search for location.." title="Type in a name">
                        </div>

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
        subheading: {
            type: String,
            required: true,
        },

    },
};
</script>

<style scoped lang="scss">
@import "../assets/scss/abstracts/mixins";
@import "../assets/scss/grid/grid";



.map {
    background-image: url("../assets/images/maps/maps.jpg");
    height: 500px;
    background-position: center;
    background-repeat: no-repeat;
    background-size: cover;

    &__subheading {
        & h2 {
            @include subheading;

        }

    }

}

#myInput {
    background-image: url('../assets/images/search-svg.svg');
    background-position: 10px 12px;
    background-repeat: no-repeat;
    width: 50%;
    font-size: 1rem;
    padding: 12px 20px 12px 40px;
    border: 1px solid #ddd;
    margin-bottom: 12px;
}


.grouping-element {
    position: absolute;
    top: 50%;
    left: 50%;
    padding: 100px 0;

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
