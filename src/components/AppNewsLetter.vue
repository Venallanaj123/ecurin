<template>
    <section class="news-letter">
        <div class="container">
            <div class="row">
                <div class="card">
                    <img class="card-image" :src="image" />
                    <div class="card-body">
                        <h4 class="post-category news-letter--title">{{ title }}</h4>
                        <div class="news-letter-element">
                            <p>• Neue Produkte testen und bewerten</p><br>
                            <p> • An attraktiven Gewinnspielen teilnehmen</p><br>
                            <p> • Aktuelle Informationen und Beratung erhalten</p>
                        </div>
                        <a href="#" class="btn btn-secondory">Newsletter abonnieren</a>

                    </div>

                </div>

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
    data: () => ({
        title: 'Eucerin Neuigkeiten abonnieren und Vorteile sichern',
        category: 'Travel',
        image: 'https://i.postimg.cc/7PnYtcHP/newsletter.jpg',
        author: 'Already Programmer',
        desc: `Indonesia with many culture`
    })

};

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import "../assets/scss/grid/grid";



.card {
    display: flex;
    flex-direction: row;
    background: $white;
    box-shadow: 0 0.1875rem 1.5rem rgba(0, 0, 0, 0.2);
    ;
    border-radius: 0.375rem;
    overflow: hidden;
    border: 1px solid $border-color;
}

.card-body {
    padding: 20px;
}

.card-image {
    max-width: 100%;
    height: auto;

}


.news-letter--title {
    @include subheading;
    text-align: left;
}

.news-letter-element p {
    margin: 2px 0;
    font-size: 1.3rem
}

.btn-secondory {
    @include button;

    text-decoration: none;
    display: block;
    width: 90%;
    border: none;
    margin-top: 20px;
    padding: 10px;
    font-size: 1.3rem;
    cursor: pointer;
    text-align: center;


}





@media (max-width: $breakpoint-xsm) {
    .card {
        grid-template-columns: auto;
        grid-template-rows: 12rem 1fr;
        flex-wrap: wrap;
    }

    .card-image {
        width: 100%;
        max-width: 400px;
        height: 300px;

    }

}
</style>
