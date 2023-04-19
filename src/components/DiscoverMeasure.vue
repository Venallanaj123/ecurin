<template>
    <section class="section-measur">


        <div class="container">
            <div class="row">
                <div class="col-12">
                    <div class="section-measur--heading">
                        <h2>Entdecke unsere Maßnahmen
                        </h2>
                    </div>

                </div>
            </div>
            <div class="row">
                <div class="col-3 ">
                    <div class="card ">


                        <img src="../assets/images/measures/euc-teaser.jpg" alt="euc-teaser">


                        <div class="card-footer">

                            <p class="card-title">Sustainable production and sourcing</p>
                            <a href="https://www.eucerin.de/nachhaltigkeit/co2-reduzierung/nachhaltige-produktion">Aenean
                                vulputate (AB), Maecena</a>

                        </div>

                    </div>
                </div>
                <div class="col-3">
                    <div class="card ">


                        <img src="../assets/images/measures/euc-teaser.jpg" alt="euc-teaser">


                        <div class="card-footer">

                            <p class="card-title">Sustainable production and sourcing</p>
                            <a href="https://www.eucerin.de/nachhaltigkeit/co2-reduzierung/nachhaltige-produktion">Aenean
                                vulputate (AB), Maecena</a>

                        </div>

                    </div>
                </div>
                <div class="col-3">
                    <div class="card ">


                        <img src="../assets/images/measures/euc-teaser.jpg" alt="euc-teaser">


                        <div class="card-footer">

                            <p class="card-title">Sustainable production and sourcing</p>
                            <a href="https://www.eucerin.de/nachhaltigkeit/co2-reduzierung/nachhaltige-produktion">Aenean
                                vulputate (AB), Maecena</a>

                        </div>

                    </div>
                </div>
                <div class="col-3  ">
                    <div class="card ">


                        <img src="../assets/images/measures/euc-teaser.jpg" alt="euc-teaser">


                        <div class="card-footer">

                            <p class="card-title">Sustainable production and sourcing</p>
                            <a href="https://www.eucerin.de/nachhaltigkeit/co2-reduzierung/nachhaltige-produktion">Aenean
                                vulputate (AB), Maecena</a>

                        </div>

                    </div>
                </div>




            </div>
        </div>
    </section>
</template>

<script>
export default {
    name: 'DiscoverMeasure',
    props: {
        msg: String
    },
    // data: function () {
    //     return {
    //         items: [
    //             {
    //                 id: 1,

    //                 desciption:
    //                     "1Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Aenean commodo ligula eget dolor. Aenean massa. Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Donec quam felis, ultricies nec, pellentesque eu, pretium quis, sem. Nulla consequat massa quis enim. ",
    //                 fullName: "Max Mustermann",
    //                 position: "Aenean vulputate (AB), Maecenas ",
    //             },
    //             {
    //                 id: 1,
    //                 desciption:
    //                     "2Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Aenean commodo ligula eget dolor. Aenean massa. Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Donec quam felis, ultricies nec, pellentesque eu, pretium quis, sem. Nulla consequat massa quis enim. ",
    //                 fullName: "Max Mustermann",
    //                 position: "Aenean vulputate (AB), Maecenas ",
    //             },
    //             {
    //                 id: 1,
    //                 desciption:
    //                     "3Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Aenean commodo ligula eget dolor. Aenean massa. Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Donec quam felis, ultricies nec, pellentesque eu, pretium quis, sem. Nulla consequat massa quis enim. ",
    //                 fullName: "Max Mustermann",
    //                 position: "Aenean vulputate (AB), Maecenas ",
    //             },


    //         ],

    //     };
    // }
}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import "../assets/scss/grid/grid";
@import "../assets/scss/grid/breakpoint";

.section-measur--heading {
    display: flex;
    justify-content: center;
    align-items: center;

    & h2 {
         font-size: 36px;
        line-height: 40px;
        color: $black-light;
    }
}

.card {
    margin: 10px;
    box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.2);
    width: 100%;
    height: 100%;

    & img {
        width: 100%;
        height: auto;
    }

    & .card-footer {
        padding: 10px;

        & .card-title {

            text-transform: uppercase;

            font-weight: 400;
            color: $grey-light;
            font-size: 12px;
        }

        & a {
            margin-bottom: 3px;

            color: $grey-light;
            font-size: 16px;

        }
    }



}


@media only screen and (max-width: $breakpoint-xsm) {

    .row {
        flex-direction: column;
        justify-content: center;
    }

}

@media only screen and (max-width: $breakpoint-m) {
    .row {
        flex-direction: column;
        justify-content: center;
    }


}
</style>
