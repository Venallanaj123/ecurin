<template>
    <header class="header">
        <nav class="navbar">
            <img src="../../assets/images/logo.svg" alt="" class="nav-logo">

            <ul class="nav-menu">

                <li class="nav-item"><a href="#" class="nav-link">Products</a></li>
                <li class="nav-item"><a href="#" class="nav-link">Advice</a></li>
                <li class="nav-item"><a href="#" class="nav-link">Research</a></li>
                <li class="nav-item"><a href="#" class="nav-link">Brand & More</a></li>
                <li class="nav-item"><a href="#" class="nav-link">sustainability</a></li>
            </ul>
            <div class="right-block">

                <span class="pta--deparatment"> <a href="https://www.side-by-side.de/"> PTA department</a></span>

                <span class="pta--flag"><img src="../../assets/images/selector-de.png" alt="block__item--flag" width="20"
                        height="20"> </span>
                <span class="pta-language">EN</span>

                <span class="pta--search"> <svg version="1.1" xmlns="http://www.w3.org/2000/svg" width="25" height="25"
                        viewBox="0 0 32 32">
                        <path
                            d="M13.455 2.182c6.226 0 11.273 5.047 11.273 11.273 0 2.851-1.058 5.454-2.803 7.439l7.483 7.485-1.029 1.029-7.485-7.483c-1.985 1.745-4.588 2.803-7.439 2.803-6.226 0-11.273-5.047-11.273-11.273s5.047-11.273 11.273-11.273zM13.455 3.636c-5.422 0-9.818 4.396-9.818 9.818s4.396 9.818 9.818 9.818c5.422 0 9.818-4.396 9.818-9.818s-4.396-9.818-9.818-9.818z">
                        </path>
                    </svg>
                </span>

            </div>
            <div class="hamburger">
                <span class="bar"></span>
                <span class="bar"></span>
                <span class="bar"></span>
            </div>
        </nav>
    </header>
</template>

<script>
export default {
    name: 'AppHeader',

}



</script>


<style scoped lang="scss">
/*@import "../../assets/scss/layout/header";*/
</style>