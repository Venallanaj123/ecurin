<template>
    <header>
        <div class="container">
            <div class="header">
                <div class="header-logo">
                    <img src="../../assets/images/logo.svg" alt="" class="nav-logo" />
                </div>
                <div class="header-left-mobile">
                    <div class="hamburger" @click="showMenuMobile()">
                        <span class="bar"></span>
                        <span class="bar"></span>
                        <span class="bar"></span>
                    </div>
                </div>
                <div class="header-logo-center">
                    <img src="../../assets/images/logo.svg" alt="" class="nav-logo" />
                </div>
                <nav class="navbar-mobile">
                    <ul class="nav-menu">
                        <!-- <li><a href="@">test</a></li> -->
                    </ul>
                </nav>

                <nav class="navbar-visible-desktop">
                    <ul class="menu">
                        <li v-for="(item, index) in menuItems" :key="index">
                            <a href="#">{{ item.title }}</a>

                            <ul v-if="item.submenu">
                                <li v-for="(subitem, index) in item.submenu" :key="index">
                                    <a href="@"> {{ subitem.title }}</a>

                                    <ul v-if="subitem.submenu">
                                        <li v-for="(subsubitem, index) in subitem.submenu" :key="index">
                                            {{ subsubitem.title }}
                                        </li>

                                    </ul>
                                </li>
                            </ul>

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
            </div>
        </div>
    </header>
</template>

<script>
export default {
    name: "AppHeader",
    components: {},
    data() {
        return {
            menuItems: [
                {
                    title: 'Item1',
                    submenu: [

                        {
                            title: "Subitem 1",
                        }
                    ]
                }
            ],
        };
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


.navbar-first-level {
    display: flex;
    justify-content: center;
    align-items: center;

    &__item {
        list-style: none;

        & a {
            color: $textcolor;
            padding: 10px;
            text-decoration: none;
            font-size: 1.6rem;
            line-height: 1.9rem;
        }
    }

    &__flyout {
        background-color: #e8eaeb;
        width: 100%;
        left: 0;
        position: absolute;
        transition: height 0.5s;
        height: 500px;
    }

    & .navbar-secondary-level__item {
        display: flex;
        padding: 0 25rem;

        & a {}

        & .nested-submenu {

            & li {
                flex-direction: column;
                margin: 16px;
                list-style-type: none;
            }

        }

    }

}







/* Add this CSS rule to hide the submenus by default */
.navbar-first-level__flyout.submenu {
    display: none;
}



/* Use the :hover pseudo-class to show the submenu when hovering over the main menu item */
ul .navbar-first-level__item:hover .navbar-first-level__flyout.submenu {
    display: block;
}


.nested-submenu {
    display: none;
}

.navbar-secondary-level__item:hover .nested-submenu {
    display: block;
}
</style>
