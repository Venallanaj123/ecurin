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

                <nav class="nvabar-visible-desktop">
                    <ul class="navbar-first-level">
                        <li v-for="(item, index) in menuItems" :key="index" class="navbar-first-level__item"
                            @mouseover="showSubmenu('submenu-1')" @mouseout="hideSubmenu('submenu-1')">
                            <a href="#">{{ item.label }}</a>
                            <ul id="submenu-1" class="navbar-first-level__flyout submenu" v-if="item.children">
                                <li v-for="(childItem, childIndex) in item.children" :key="childIndex"
                                    class="navbar-secondary-level__item">
                                    <a href="#">{{ childItem.label }}</a>
                                    <!-- <ul
                    class="nested-submenu"
                    :id="'nested-submenu-' + index + '-' + childIndex"
                  >
                    <li
                      v-for="(
                        nestedChildItem, nestedChildIndex
                      ) in childItem.children"
                      :key="nestedChildIndex"
                    >
                      <a href="#">{{ nestedChildItem.label }}</a>
                    </li>
                  </ul> -->
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
                    label: "Menu Item 1",
                    children: [
                        {
                            label: "Subemenu 10",
                        },
                    ],
                },
                {
                    label: "Menu Item 2",
                    children: [
                        {
                            label: "Submenu Item 2",
                            children: [
                                {
                                    label: "Nested Submenu Item 4",
                                },
                                {
                                    label: "Nested Submenu Item 2",
                                },
                            ],
                        },
                        {
                            label: "Submenu Item 2",
                            children: [
                                {
                                    label: "Nested Submenu Item 1",
                                },
                                {
                                    label: "Nested Submenu Item 2",
                                },
                            ],
                        },
                    ],
                },
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

        showSubmenu(submenuId) {
            document.getElementById(submenuId).style.display = "block";
            document.getElementById(submenuId).style.height = "770px";
            /*document.getElementById(submenuId).style.transition.height = "0.3s ease";*/
        },

        hideSubmenu(submenuId) {
            document.getElementById(submenuId).style.display = "none";
        },
    },
};
</script>

<style scoped lang="scss">
@import "../../assets/scss/layout/header";

/* Strat to style na-menu for mobile */

.navbar-first-level__flyout {
    display: none;
}

.navbar-first-level__flyout {
    background-color: #e8eaeb;
    width: 100%;
    height: 500px;
    left: 0;
    position: absolute;
    display: block;

    & li {
        display: flex;
        list-style: none;
    }
}

ul {
    display: flex;
    justify-content: center;
    align-items: center;

    & li {
        list-style: none;
    }

    & a {
        color: $textcolor;
        display: block;
        padding: 10px 5px;
        text-decoration: none;
        text-decoration: none;
        font-size: 1.6rem;
        line-height: 1.9rem;
        margin: 0 13px;
    }
}

ul .submenu li .arrow-right::after {
    border: solid $danger;
    border-width: 0 2px 2px 0;
    display: inline-block;
    padding: 3px;
    content: "";
    transform: rotate(-45deg);
    -webkit-transform: rotate(-45deg);
}
</style>
