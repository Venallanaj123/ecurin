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
                            <li><a href="@">test</a></li>
                        </ul>
                    </nav>
                    <!-- Start to create menu for desktop-->
                    <nav class="nvabar-visible-desktop">
                        <ul class="navbar-first-level">
                            <!-- Start Menu Products-->
                            <li>
                                <a href="#">Products</a>


                                <ul class="navbar-second-level submenu">
                                    <li class="menu-item-active">
                                        <a href="#" class="arrow-right">Product Line</a>
                                        <ul class=" navbar-third-level  nested-submenu">
                                            <li><a href="https://www.eucerin.de/produkte/actinic-control">Actinic
                                                    Control</a>
                                            </li>
                                            <li>
                                                <a href="https://www.eucerin.de/produkte/actinic-control">Actinic
                                                    Control</a>
                                            </li>
                                            <li>
                                                <a href="https://www.eucerin.de/produkte/actinic-control">Actinic
                                                    Control</a>
                                            </li>
                                            <li>
                                                <a href="https://www.eucerin.de/produkte/actinic-control">Actinic
                                                    Control</a>
                                            </li>
                                            <li>
                                                <a href="https://www.eucerin.de/produkte/actinic-control">Actinic
                                                    Control</a>
                                            </li>
                                            <li>
                                                <a href="https://www.eucerin.de/produkte/actinic-control">Actinic
                                                    Control</a>
                                            </li>
                                            <li>
                                                <a href="https://www.eucerin.de/produkte/actinic-control">Actinic
                                                    Control</a>
                                            </li>
                                            <li>
                                                <a href="https://www.eucerin.de/produkte/actinic-control">Actinic
                                                    Control</a>
                                            </li>
                                            <li>
                                                <a href="https://www.eucerin.de/produkte/actinic-control">Actinic
                                                    Control</a>
                                            </li>
                                            <li>
                                                <a href="https://www.eucerin.de/produkte/actinic-control">Actinic
                                                    Control</a>
                                            </li>
                                            <li>
                                                <a href="https://www.eucerin.de/produkte/actinic-control">Actinic
                                                    Control</a>
                                            </li>
                                        </ul>
                                    </li>
                                    <li>
                                        <a href="#" class="arrow-right">skin condition</a>
                                        <ul class="nested-submenu">


                                            <li><a href="https://www.eucerin.de/produkte/anti-age">anti age</a></li>
                                            <li><a href="https://www.eucerin.de/produkte/anti-age">anti age</a></li>
                                            <li><a href="https://www.eucerin.de/produkte/anti-age">anti age</a></li>
                                            <li><a href="https://www.eucerin.de/produkte/anti-age">anti age</a></li>
                                            <li><a href="https://www.eucerin.de/produkte/anti-age">anti age</a></li>

                                        </ul>
                                    </li>
                                </ul>

                            </li>

                            <!-- End Menu Products-->

                            <!-- Start Menu Advice-->
                            <li>
                                <a href="#">Advice</a>
                                <ul class="submenu">
                                    <li>
                                        <a href="#" class="arrow-right">Skin condition</a>
                                        <ul class="nested-submenu">
                                            <li>

                                                <a href="/hautzustand/anti-age">
                                                    <font style="vertical-align: inherit;">
                                                        <font style="vertical-align: inherit;">anti age</font>
                                                    </font>
                                                </a>

                                            </li>
                                            <li>

                                                <a href="/hautzustand/trockene-haut">
                                                    <font style="vertical-align: inherit;">
                                                        <font style="vertical-align: inherit;">Dry skin</font>
                                                    </font>
                                                </a>
                                            </li>
                                            <li>

                                                <a href="/hautzustand/neurodermitis">
                                                    <font style="vertical-align: inherit;">
                                                        <font style="vertical-align: inherit;">neurodermatitis</font>
                                                    </font>
                                                </a>

                                            </li>
                                            <li>
                                                <a href="/hautzustand/unreine-haut">
                                                    <font style="vertical-align: inherit;">
                                                        <font style="vertical-align: inherit;">Blemished skin</font>
                                                    </font>
                                                </a>
                                            </li>
                                            <li>
                                                <a href="/hautzustand/roetungen-im-gesicht">
                                                    <font style="vertical-align: inherit;">
                                                        <font style="vertical-align: inherit;">reddening of the face</font>
                                                    </font>
                                                </a>

                                            </li>
                                            <li>

                                                <a href="/hautzustand/empfindliche-haut">
                                                    <font style="vertical-align: inherit;">
                                                        <font style="vertical-align: inherit;">Sensitive skin</font>
                                                    </font>
                                                </a>

                                            </li>
                                            <li>

                                                <a href="/hautzustand/sonnenschutz">
                                                    <font style="vertical-align: inherit;">
                                                        <font style="vertical-align: inherit;">sun protection</font>
                                                    </font>
                                                </a>

                                            </li>
                                            <li>

                                                <a href="/hautzustand/pigmentflecken-hyperpigmentierung">
                                                    <font style="vertical-align: inherit;">
                                                        <font style="vertical-align: inherit;">Pigment spots &amp;
                                                            hyperpigmentation</font>
                                                    </font>
                                                </a>
                                            </li>
                                            <li> <a href="/hautzustand/schwitzen">
                                                    <font style="vertical-align: inherit;">
                                                        <font style="vertical-align: inherit;">Sweating &amp; deodorant
                                                            intolerance</font>
                                                    </font>
                                                </a>

                                            </li>
                                            <li>

                                                <a href="/hautzustand/diabetische-haut">
                                                    <font style="vertical-align: inherit;">
                                                        <font style="vertical-align: inherit;">diabetic skin</font>
                                                    </font>
                                                </a>

                                            </li>
                                            <li>  <a href="/hautzustand">
                                                    <font style="vertical-align: inherit;">
                                                        <font style="vertical-align: inherit;">all articles</font>
                                                    </font>
                                                </a>

                                            </li>

                                        </ul>
                                    </li>
                                    <li>
                                        <a href="#" class="arrow-right">useful information</a>
                                        <ul class="nested-submenu">


                                            <li><a href="https://www.eucerin.de/produkte/anti-age">skin knowledge</a></li>
                                            <li><a href="https://www.eucerin.de/produkte/anti-age">skin care</a></li>
                                            <li><a href="https://www.eucerin.de/produkte/anti-age">skin indications</a></li>
                                            <li><a href="https://www.eucerin.de/produkte/anti-age">all articles</a></li>

                                        </ul>
                                    </li>
                                </ul>
                            </li>

                            <!--End Menu Advice-->


                            <!--Start Menu Resarch-->
                            <li> <a href="https://www.eucerin.de/unsere-forschung/aus-der-forschung">Research</a>
                                <ul class="submenu">
                                    <li> <a href="https://www.eucerin.de/unsere-forschung/aus-der-forschung">Science behind the
                                            product lines</a></li>
                                    <li>
                                        <a href="https://www.eucerin.de/unsere-forschung/forschungshintergrund">About our
                                            research
                                        </a>
                                    </li>
                                    <li>
                                        <a href="https://www.eucerin.de/unsere-forschung/datenbank-fuer-inhaltsstoffe">Our
                                            ingredients
                                        </a>
                                    </li>
                                </ul>
                            </li>
                            <!--Endt Menu Resarch-->

                            <!--Start Menu Brand more-->
                            <li> <a href="#">Brand & More</a>
                                <ul class="submenu">
                                    <li>
                                        <a href="https://www.eucerin.de/ueber-eucerin/purpose">Eucerin's purpose</a>
                                    </li>

                                    <li>
                                        <a href="#">
                                            Anti-aging refill capsules</a>
                                    </li>

                                    <li>
                                        <a href="#">
                                            Body care for dry skin
                                        </a>
                                    </li>
                                    <li>
                                        <a href="#"> mothers day promo </a>
                                    </li>
                                    <li>
                                        <a href="#">
                                            #1 against pigment spots
                                        </a>
                                    </li>
                                    <li>
                                        <a href="/specials/dermopure"> #MYSKINNOFILTER </a>
                                    </li>
                                    <li>
                                        <a href="/specials/hyfi-gold-relaunch">
                                            HYALURON-FILLER + ELASTICITY with a new formula
                                        </a>
                                    </li>
                                    <li>
                                        <a href="/specials/aquaphor">
                                            Aquaphor Protect &amp; Repai
                                        </a>
                                    </li>
                                    <li>
                                        <a href="/specials/hautkrebs-vorsorge-sonnenschutz">
                                            skin cancer prevention
                                        </a>
                                    </li>
                                    <li>
                                        <a href="/specials/urearepair-hautvertrauen">
                                            UreaRepair skin trust
                                        </a>
                                    </li>
                                    <li class="menu-aim__item no-subnav">
                                        <a href="/specials/neurodermitis-atopicontrol">
                                            Atopic dermatitis care
                                        </a>
                                    </li>
                                    <li>
                                        <a href="/specials/socialmission"> social mission </a>
                                    </li>
                                    <li>
                                        <a href="/specials/generationeucerin">
                                            #generationEucerin
                                        </a>
                                    </li>
                                    <li>
                                        <a href="/specials/frauenstudie"> women study </a>
                                    </li>
                                    <li>
                                        <a href="/specials/digitale-hautarzt-diagnose">
                                            Dermanostic
                                        </a>
                                    </li>
                                    <li>
                                        <a href="/meta-pages/eucerin-treuekarte" target="_blank" rel="noopener noreferrer">
                                            loyalty progra
                                        </a>
                                    </li>
                                    <li>
                                        <a href="/specials/anton"> Anton </a>
                                    </li>

                                </ul>

                            </li>
                            <!--End Menu Brand more-->

                            <!--Start Menu sustainability -->

                            <li> <a href="#">sustainability</a>
                                <ul class="submenu">
                                    <li><a href="https://www.eucerin.de/nachhaltigkeit/co2-reduzierung" class="arrow-right">CO2
                                            reduction</a>
                                        <ul class="nested-submenu">
                                            <li>
                                                <a href="#">
                                                    <font style="vertical-align: inherit;">
                                                        <font style="vertical-align: inherit;">Sustainable packaging</font>
                                                    </font>
                                                </a>
                                            </li>
                                            <li>

                                                <a href="#">
                                                    <font style="vertical-align: inherit;">
                                                        <font style="vertical-align: inherit;">climate protection</font>
                                                    </font>
                                                </a>
                                            </li>
                                            <li>
                                                <a href="#">
                                                    <font style="vertical-align: inherit;">
                                                        <font style="vertical-align: inherit;">sustainable production</font>
                                                    </font>
                                                </a>

                                            </li>

                                        </ul>

                                    </li>
                                    <li><a href="#" class="arrow-right">High quality ingredients</a>
                                        <ul class="nested-submenu">
                                            <li>
                                                <a href="/nachhaltigkeit/hochwertige-inhaltsstoffe/nachhaltiger-palmoel-anbau">
                                                    <font style="vertical-align: inherit;">
                                                        <font style="vertical-align: inherit;">Sustainable palm oil cultivation
                                                        </font>
                                                    </font>
                                                </a>

                                            </li>
                                            <li>

                                                <a href="/nachhaltigkeit/hochwertige-inhaltsstoffe/kosmetik-ohne-tierversuche">
                                                    <font style="vertical-align: inherit;">
                                                        <font style="vertical-align: inherit;">Cosmetics without animal testing
                                                        </font>
                                                    </font>
                                                </a>
                                            </li>
                                            <li>
                                                <a href="/nachhaltigkeit/hochwertige-inhaltsstoffe/kosmetik-ohne-mikroplastik">
                                                    <font style="vertical-align: inherit;">
                                                        <font style="vertical-align: inherit;">Cosmetics without microplastics
                                                        </font>
                                                    </font>
                                                </a>
                                            </li>
                                        </ul>
                                    </li>
                                </ul>
                            </li>
                            <!--End Menu sustainability -->

                        </ul>
                    </nav>


                    <!-- End to create menu for desktop-->



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
    name: 'HelloWorld',
    props: {
        msg: String
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import "../../assets/scss/layout/header";

/* Strat to style na-menu for mobile */

nav ul {
    display: flex;
    justify-content: space-between;
    align-items: center;
    list-style: none;
    margin: 0;
    padding: 0;
}

nav li {
    /*display: inline-block;*/

    position: relative;
}

nav a {
    color: $textcolor;
    display: block;
    padding: 10px 5px;
    text-decoration: none;
}

nav a:hover {
    background-color: white !important;
}

.submenu {
    display: none;
    position: absolute;
    top: 100%;
    left: 0;
    background-color: white;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);

}

.nested-submenu {
    display: none;
    position: absolute;
    top: 0;
    left: 100%;
    background-color: white;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);
}

li:hover>.submenu {
    display: block;
}

li:hover>.nested-submenu {
    display: block;
}

.arrow {
    display: inline-block;
    margin-left: 5px;
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

/*Start to style Mega Menu*/

ul {
    margin: 0;
    padding: 0;
    list-style: none;
}

a {
    text-decoration: none;
    color: #000;
    font-size: 1.6rem;
    line-height: 1.9rem;
    padding: 30px 0;
    margin: 0 13px;
}

.nav-menu {
    display: flex;
}

.nav-mega-submenu ul li {
    margin: 1.6rem 0;
}

.nav-menu li.nav-mega-menu .nav-mega-submenu {
    display: none;
    position: absolute;
    top: 70px;
    left: 0;
    z-index: 10;
    background-color: #fff;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);
    cursor: pointer;
    width: 100vw;
}

.nav-menu li.nav-mega-menu:hover .nav-mega-submenu {
    display: block;
}

.nav-mega-submenu {
    padding: 25px;
    width: 100%;
    padding: 4rem 30rem;
}

.nav-item li {
    margin: 1.6rem 0;
}

.nav-item li a:hover {
    color: $danger !important;
}

.nav-mega-submenu {
    opacity: 0;
    transform: translateY(-20px);
    transition: all 0.3s ease-in-out;
}

.nav-menu li.nav-mega-menu:hover .nav-mega-submenu {
    opacity: 1;
    transform: translateY(0);
}
</style>
