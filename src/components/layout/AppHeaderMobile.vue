<template>
    <header>
        <div class="container">
            <div class="header">
                <img src="../../assets/images/logo.svg" alt="" class="nav-logo" />
                <nav class="navbar">
                    <ul class="nav-menu">
                        <li><a href="#">Products</a></li>
                        <li><a href="#">Advice</a></li>
                        <li><a href="#">Research</a></li>
                        <li>
                            <a href="#">Brand & More</a>
                        </li>
                        <li>
                            <a href="#">sustainability</a>
                        </li>
                    </ul>
                </nav>
            </div>
        </div>
    </header>
</template>

<script>
export default {
    name: "AppHeaderMobile",

    methods: {
        showMenuMobile() {
            debugger;
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
/*@import "../../assets/scss/layout/header";*/
</style>
