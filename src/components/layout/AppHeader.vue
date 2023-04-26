<template>
    <header>
        <div class="container">
            <div class="header">
                <img src="../../assets/images/logo.svg" alt="" class="nav-logo" />
                <nav class="navbar">
                    <ul class="nav-menu">
                        <li class="has-mega-menu">
                            <a href="#">Products</a>

                            <div class="mega-menu ">
                                <div class="submenu">
                                    <ul>
                                        <li><a href="#">product line</a></li>
                                        <li><a href="#">skin condition</a></li>
                                    </ul>

                                </div>
                            </div>
                        </li>
                        <li class="has-mega-menu"><a href="#">Products1</a>

                            <div class="mega-menu">
                                <div class="submenu">
                                    <ul>
                                        <li><a href="#">product line2s</a></li>
                                        <li><a href="#">skin condition</a></li>
                                    </ul>

                                </div>
                            </div>
                        </li>

                    </ul>
                </nav>
                <div class="right-block">
                    <span class="pta--deparatment">
                        <a href="https://www.side-by-side.de/"> PTA department</a></span>

                    <span class="pta--flag"><img src="../../assets/images/selector-de.png" alt="block__item--flag"
                            width="20px" height="20px" />
                    </span>
                    <span class="pta-language">EN</span>

                    <span class="pta--search">
                        <svg version="1.1" xmlns="http://www.w3.org/2000/svg" width="25" height="25" viewBox="0 0 32 32">
                            <path
                                d="M13.455 2.182c6.226 0 11.273 5.047 11.273 11.273 0 2.851-1.058 5.454-2.803 7.439l7.483 7.485-1.029 1.029-7.485-7.483c-1.985 1.745-4.588 2.803-7.439 2.803-6.226 0-11.273-5.047-11.273-11.273s5.047-11.273 11.273-11.273zM13.455 3.636c-5.422 0-9.818 4.396-9.818 9.818s4.396 9.818 9.818 9.818c5.422 0 9.818-4.396 9.818-9.818s-4.396-9.818-9.818-9.818z">
                            </path>
                        </svg>
                    </span>
                </div>
                <!-- <AppHeaderMobileVue /> -->
                <div class="hamburger" @click="showMenuMobile()">
                    <span class="bar"></span>
                    <span class="bar"></span>
                    <span class="bar"></span>
                </div>
            </div>
        </div>
    </header>
</template>

<script>
// import AppHeaderMobile from './AppHeaderMobile.vue';
export default {
    name: "AppHeader",
    components: {

    },


    methods: {
        showMenuMobile() {

            let showMenuMobile;
            let hamburger = document.querySelector(".hamburger");
            let navMenu = document.querySelector(".nav-menu");

            hamburger.addEventListener("click", showMenuMobile);

            hamburger.classList.toggle("active");
            navMenu.classList.toggle("active");
        },
    },
};
</script>

<style scoped lang="scss">
@import "../../assets/scss/layout/header";




/*ul li a::after {

    border: solid rgb(153, 76, 76);
    border-width: 0 3px 3px 0;
    display: inline-block;
    padding: 3px;
    content: "";
    transform: rotate(-45deg);
    -webkit-transform: rotate(-45deg);
}*/
</style>
