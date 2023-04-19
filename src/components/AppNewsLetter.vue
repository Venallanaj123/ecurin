<template>
    <section class="news-letter">
        <div class="container">
            <div class="row">
                <div class="col-12">
                    <div class="card">
                        <img :src="image" alt="logo_brand" class="logo_brand" />
                        <!-- <div class="card-body">
                            <h5 class="card-title">Card Title</h5>
                            <p class="card-text">This is a sample card text.</p>
                            <a href="#" class="btn btn-primary">Learn More</a>
                        </div> -->

                    </div>
                </div>
                <!-- <div class="col-6">
                    col-6
                </div> -->
            </div>
        </div>

    </section>
</template>

<script>
import image from "../assets/images/newsletter/newsletter.jpg";
export default {
    name: 'AppNewsLetter',
    props: {
        msg: String
    },
    data: function () {
        return {
            // items: [
            //     {
            //         id: 1,
            //         desciption:
            //             "Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Aenean commodo ligula eget dolor. Aenean massa. Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Donec quam felis, ultricies nec, pellentesque eu, pretium quis, sem. Nulla consequat massa quis enim. ",
            //         fullName: "Max Mustermann",
            //         position: "Aenean vulputate (AB), Maecenas ",
            //     },
            //     {
            //         id: 2,
            //         desciption:
            //             "222Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Aenean commodo ligula eget dolor. Aenean massa. Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Donec quam felis, ultricies nec, pellentesque eu, pretium quis, sem. Nulla consequat massa quis enim. ",
            //         fullName: "Max Mustermann",
            //         position: "Aenean vulputate (AB), Maecenas ",
            //     },
            //     {
            //         id: 3,
            //         desciption:
            //             "22266Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Aenean commodo ligula eget dolor. Aenean massa. Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Donec quam felis, ultricies nec, pellentesque eu, pretium quis, sem. Nulla consequat massa quis enim. ",
            //         fullName: "Max Mustermann",
            //         position: "Aenean vulputate (AB), Maecenas ",
            //     },
            // ],
            image: image,

        };
    },
};

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import "../assets/scss/grid/grid";
</style>
