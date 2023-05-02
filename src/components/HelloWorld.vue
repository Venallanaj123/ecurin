<template>
    <template>
        <div class="navigation">
            <ul>
                <li v-for="(item, index) in items" :key="index">
                    {{ item.name }}
                    <ul v-if="item.children && item.children.length > 0">
                        <li v-for="(childItem, childIndex) in item.children" :key="childIndex">
                            {{ childItem.name }}
                            <ul v-if="childItem.children && childItem.children.length > 0">
                                <li v-for="(subChildItem, subChildIndex) in childItem.children" :key="subChildIndex">
                                    {{ subChildItem.name }}
                                </li>
                            </ul>
                        </li>
                    </ul>
                </li>
            </ul>
        </div>
    </template>
</template>

<script>
export default {
    name: 'HelloWorld',
    data() {
        return {
            items: [
                {
                    name: 'Home',
                    children: []
                },
                {
                    name: 'Products',
                    children: [
                        {
                            name: 'Product Line',
                            children: [
                                {
                                    name: 'Submenu Item'
                                }
                            ]
                        }
                    ]
                },
                {
                    name: 'About',
                    children: []
                },
                {
                    name: 'Contact',
                    children: []
                }
            ]
        };
    }
};
</script>


<style scoped lang="scss">
@import "../../assets/scss/layout/header";

/* Strat to style na-menu for mobile */

.navbar-first-level {
    display: flex;
    align-items: center;
    justify-content: center;
}

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

    /* display: flex;
    justify-content: center;
    align-items: center;*/

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
