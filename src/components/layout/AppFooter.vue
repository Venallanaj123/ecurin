<template>
    <footer>
        <div class="container">
            <div class="footer">
                <div class="row">
                    <div class="span_2_of_2">
                        <div class="footer__logo">
                            <img src="../../assets/images/logo.svg" class="footer_logo--ecurin" alt="brand logo ecurin" />
                        </div>
                    </div>
                </div>
                <div class="row">
                    <div class="span_2_of_2">
                        <div class="footer__social">
                            <a href="#" class="footer__social-item footer__social-item--facebook">
                                <img src="../../assets/images/facebook.svg" alt="" width="25px" height="25px" />
                            </a>
                            <a href="#" class="footer__social-item footer__social-item--instagram">
                                <img src="../../assets/images/instagram.svg" alt="" width="25px" height="25px" />
                            </a>
                            <a href="#" class="footer__social-item footer__social-item--tiktok">
                                <img src="../../assets/images/youtube.svg" alt="" width="25px" height="25px" />
                            </a>
                            <a href="#" class="footer__social-item footer__social-item--tiktok">
                                <img src="../../assets/images/pinterest.svg" alt="" width="25px" height="25px" />
                            </a>
                            <a href="#" class="footer__social-item footer__social-item--tiktok">
                                <img src="../../assets/images/tiktok.svg" alt="" width="25px" height="25px" />
                            </a>
                        </div>
                    </div>
                </div>

                <div class="row">
                    <div class="span_2_of_2">
                        <nav class="footer__nav">
                            <ul class="footer__menu">
                                <li class="footer__menu-item"><a href="#">Contact</a></li>
                                <li class="footer__menu-item"><a href="#">imprint</a></li>
                                <li class="footer__menu-item">
                                    <a href="#">Data protection</a>
                                </li>
                                <li class="footer__menu-item"><a href="#">Terms of Use</a></li>
                                <li class="footer__menu-item">
                                    <a href="#">Cookies settings</a>
                                </li>
                            </ul>
                        </nav>
                    </div>
                </div>
                <hr class="hr" />
                <div class="footer__bottom">
                    <div class="row">
                        <div class="span_1_of_2">
                            <div class="footer__bottom--left">
                                <img src="../../assets/images/Beiersdorf-Logo.png" alt="" />
                            </div>
                        </div>
                        <div class="span_1_of_2">
                            <div class="footer__bottom--right">
                                <nav class="footer__nav">
                                    <ul>
                                        <li><a href="#">About Us</a></li>
                                        <li><a href="#">About Us</a></li>
                                    </ul>
                                </nav>
                                <p class="footer__nav--copyright">
                                    COPYRIGHT © BEIERSDORF 2023
                                </p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </footer>
</template>

<script>
export default {
    name: "AppFooter",
};
</script>

<style scoped lang="scss">
@import "../../assets/scss/grid/grid";

footer {
    // padding-top: 2rem;
    padding-bottom: 5rem;
    position: relative;

    & .footer {
        padding: 5rem 0;
        width: 80%;
        margin: 0 auto;

        &__logo {
            display: flex;
            align-items: center;
            justify-content: center;

            & img {
                width: 100%;
                max-width: 10rem;
                height: auto;
            }
        }

        &__social {
            display: flex;
            justify-content: center;
            align-items: center;
            margin-top: 1rem;

            & a {
                padding: 0 1rem;
            }
        }

        & .hr {
           
        }

        &__nav {
            margin-top: 3rem;

            & ul {
                display: flex;
                justify-content: center;
                align-items: center;
            }

            & li {
                list-style: none;
                padding: 0 0.5rem;
            }

            & a {
                text-transform: uppercase;
                font-size: 1.2rem;
                line-height: 1.5rem;
                color: $grey-light;
                font-weight: 400;
                transition: all 0.3s;
                text-decoration: underline #a7adb3;
            }

            & a:hover {
                text-decoration: none;
            }
        }

        &__bottom {
            margin-top: 3rem;
            // width: 100rem;

            &--left {
                & img {
                    width: 100%;
                    max-width: 10rem;
                    height: auto;
                }
            }

            &--right {
                display: flex;
                justify-content: flex-end;
                align-items: center;

                & nav {
                    margin-top: 0;
                }
            }
        }
    }
}
</style>
