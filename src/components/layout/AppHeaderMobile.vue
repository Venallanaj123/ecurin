<template>
    <header>
        <nav>
            <ul>
                <li v-for="(menuItem, index) in menuItems" :key="index">
                    <a :href="menuItem.link">{{ menuItem.label }}</a>
                    <ul class="submenu" v-if="menuItem.submenu">
                        <li v-for="(subMenuItem, subIndex) in menuItem.submenu" :key="subIndex"
                            v-on:mouseover="showSubMenu(index, true)" v-on:mouseleave="showSubMenu(index, false)">
                            <a :href="subMenuItem.link">{{ subMenuItem.label }}</a>
                            <ul class="nested-submenu" v-show="selectedSubMenuIndex === index && showNestedMenu">
                                <li v-for="(nestedMenuItem, nestedIndex) in subMenuItem.submenu" :key="nestedIndex">
                                    <a :href="nestedMenuItem.link">{{ nestedMenuItem.label }}</a>
                                </li>
                            </ul>
                            <span class="arrow" v-show="selectedSubMenuIndex === index && showNestedMenu">></span>
                        </li>
                    </ul>
                    <span class="arrow" v-if="menuItem.submenu">></span>
                </li>
            </ul>
        </nav>
    </header>
</template>

<script>
export default {
    name: "AppHeaderMobile",
    data() {
        return {
            menuItems: [
                {
                    label: "Products",
                    link: "#",
                    submenu: [
                        {
                            label: "Product Line",
                            link: "#",
                            submenu: [
                                { label: "Product A", link: "#" },
                                { label: "Product B", link: "#" },
                                { label: "Product C", link: "#" },
                            ],
                        },
                        // { label: "Product X", link: "#" },
                        // { label: "Product Y", link: "#" },
                        // { label: "Product Z", link: "#" },
                    ],
                },
                { label: "Contact Us", link: "#" },
            ],
            selectedSubMenuIndex: -1,
            showNestedMenu: false,
        };
    },
    methods: {
        showSubMenu(index, value) {
            this.selectedSubMenuIndex = value ? index : -1;
            this.showNestedMenu = value;
        },
    },
};
</script>

<style scoped lang="scss">
@import "../../assets/scss/layout/header";

/* Strat to style na-menu for mobile */

.navbar-first-level__flyout {
    /* display: none;*/
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

    // display: flex;
    // justify-content: center;
    // align-items: center;
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

.arrow {
    margin-left: 5px;
    display: inline-block;
    width: 10px;
    height: 10px;
    border-top: 2px solid #000;
    border-right: 2px solid #000;
    transform: rotate(45deg);
}
</style>
