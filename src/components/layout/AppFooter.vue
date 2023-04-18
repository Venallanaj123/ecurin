<template>
    <footer class="footer">
        <div class="footer-container">
            <div class="row">

                <div class="footer__logo">
                    <img src="../../assets/images/logo.svg" class="footer_logo--ecurin" alt="brand logo ecurin">

                </div>

            </div>
            <div class="row">
                <div class="col-lg-12">
                    <div class="footer__social">
                        <a href="#" class="footer__social-item footer__social-item--facebook">
                            <img src="../../assets/images/facebook.svg" alt="" width="25px" height="25px">
                        </a>
                        <a href="#" class="footer__social-item footer__social-item--instagram">
                            <img src="../../assets/images/instagram.svg" alt="" width="25px" height="25px">
                        </a>
                        <a href="#" class="footer__social-item footer__social-item--tiktok">
                            <img src="../../assets/images/youtube.svg" alt="" width="25px" height="25px">
                        </a>
                        <a href="#" class="footer__social-item footer__social-item--tiktok">
                            <img src="../../assets/images/pinterest.svg" alt="" width="25px" height="25px">
                        </a>
                        <a href="#" class="footer__social-item footer__social-item--tiktok">
                            <img src="../../assets/images/tiktok.svg" alt="" width="25px" height="25px">
                        </a>

                    </div>

                </div>
            </div>

            <div class="row">
                <div class="col-lg-12">
                    <nav class="footer__nav">
                        <ul class="footer__menu">
                            <li class="footer__menu-item"><a href="#">Contact</a></li>
                            <li class="footer__menu-item"><a href="#">imprint</a></li>
                            <li class="footer__menu-item"><a href="#">Data protection</a></li>
                            <li class="footer__menu-item"><a href="#">Terms of Use</a></li>
                            <li class="footer__menu-item"><a href="#">Cookies settings</a></li>
                        </ul>
                    </nav>
                </div>
            </div>


        </div>





    </footer>
</template>

<script>
export default {
    name: 'AppFooter',

}
</script>


<style scoped lang="scss">
@import "../../assets/scss/grid/grid";

.footer {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    align-items: center;
    background-color: #f5f5f5;
    position: relative;
    padding: 10rem 0;

    &__logo {
        /* @include center;*/
    }

    &__social {

        @include center;
        margin: 50px 0;


        & a {
            padding-left: 10px;
            padding-right: 10px;
        }
    }

    &__nav {
        @include center;
        margin-top: 100px;



        & ul {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        & li {
            list-style: none;
            padding: 0 1rem;
            font-size: 1rem;
        }

        & a {
            text-transform: uppercase;
            font-family: " Roboto-Light";
            font-size: 1.2rem;
            line-height: 1rem;
            color: $grey-light;
            font-weight: 400;
        }

        & a:hover {
            text-decoration: none;
        }

    }

}

@media only screen and (max-width: 768px) {
    .footer {
        &__nav {

            & ul {
                flex-direction: column;
                text-align: center;
                margin-top: 100px;
            }

            & li {
                margin: 5px 0;
            }



        }
    }
}
</style>