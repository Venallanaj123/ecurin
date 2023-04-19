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

$bg: #eedfcc;
$text: #777;
$black: #121212;
$white: #fff;
$red: #e04f62;
$border: #ebebeb;
$shadow: rgba(0, 0, 0, 0.2);

.card {
    display: flex;
    flex-direction: row;
    background: $white;
    box-shadow: 0 0.1875rem 1.5rem $shadow;
    border-radius: 0.375rem;
    overflow: hidden;
}

.card-image {
    height: auto;
    max-width: 100%;
}


.news-letter--title {
    @include subheading;
    text-align: left;
}

.news-letter-element p {
    margin: 5px 0;
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

@media (max-width: 40rem) {
    #root {
        width: 18rem;
        height: 27.25rem;
    }

    .card {
        flex-wrap: wrap;
    }
}

@supports (display: grid) {
    body {
        display: grid;
        grid-template-columns: repeat(4, 1fr);
        grid-gap: 0.625rem;
        grid-template-areas: ". main main ." ". main main .";
    }

    #root {
        grid-area: main;
        align-self: center;
        justify-self: center;
    }

    .card-image {
        height: 100%;
    }

    .card {
        display: grid;
        grid-template-columns: 1fr 1fr;
        grid-template-rows: 1fr;
    }

    @media (max-width: 40rem) {
        .card {
            grid-template-columns: auto;
            grid-template-rows: 12rem 1fr;
        }
    }
}
</style>
