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

        <nav class=" navbar visible-desktop">
          <ul class="nav-menu ">
            <li class="nav-mega-menu">
              <a href="#">Products</a>
              <div class="nav-mega-submenu">
                <ul class="nav-item-arrow">
                  <li><a href="https://www.eucerin.de/hautzustand">product line</a>

                  </li>
                  <li><a href="https://www.eucerin.de/hautzustand">skin condition</a></li>
                </ul>

              </div>
            </li>


            <li class="nav-mega-menu">
              <a href="#">Advice</a>
              <div class=" nav-mega-submenu  ">
                <ul class="nav-item-arrow">
                  <li><a href="https://www.eucerin.de/hautzustand">skin condition</a></li>
                  <li><a href="https://www.eucerin.de/hautzustand">useful information</a></li>
                </ul>
              </div>
            </li>
            <li class="nav-mega-menu">
              <a href="#">Brand & More</a>
              <div class=" nav-mega-submenu  ">
                <ul class="nav-item">
                  <li><a href="https://www.eucerin.de/ueber-eucerin/purpose">Eucerin's purpose</a></li>

                  <li><a href="/specials/anti-age-refill"> Anti-aging refill capsules</a> </li>

                  <li>

                    <a href="/specials/koerperpflege-bei-trockener-haut">
                      Body care for dry skin
                    </a>
                  </li>
                  <li>

                    <a href="/specials/muttertag">
                      mothers day promo
                    </a>

                  </li>
                  <li>

                    <a href="/specials/uncover-antipigment">
                      #1 against pigment spots
                    </a>

                  </li>
                  <li>

                    <a href="/specials/dermopure">
                      #MYSKINNOFILTER
                    </a>
                  </li>
                  <li>

                    <a href="/specials/hyfi-gold-relaunch">
                      HYALURON-FILLER + ELASTICITY with a
                      new formula
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
                  <li> <a href="/specials/urearepair-hautvertrauen">
                      UreaRepair skin trust
                    </a>

                  </li>
                  <li class="menu-aim__item no-subnav">

                    <a href="/specials/neurodermitis-atopicontrol">
                      Atopic dermatitis care
                    </a>

                  </li>
                  <li>

                    <a href="/specials/socialmission">
                      social mission
                    </a>
                  </li>
                  <li>

                    <a href="/specials/generationeucerin">
                      #generationEucerin
                    </a>
                  </li>
                  <li>

                    <a href="/specials/frauenstudie">
                      women study
                    </a>
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

                    <a href="/specials/anton">
                      Anton
                    </a>
                  </li>

                </ul>

              </div>
            </li>

            <li class="nav-mega-menu">
              <a href="https://www.eucerin.de/unsere-forschung/aus-der-forschung">Research</a>
              <div class="nav-mega-submenu">
                <ul class="nav-item">
                  <li><a href="https://www.eucerin.de/unsere-forschung/aus-der-forschung">Science behind the product
                      lines</a></li>
                  <li><a href="https://www.eucerin.de/unsere-forschung/forschungshintergrund">About our research
                    </a></li>
                  <li><a href="https://www.eucerin.de/unsere-forschung/datenbank-fuer-inhaltsstoffe">Our ingredients
                    </a></li>


                </ul>
              </div>
            </li>
            <li class="nav-mega-menu">
              <a href="#">sustainability</a>
              <div class="nav-mega-submenu">
                <ul class="nav-item-arrow">
                  <li><a href="#">CO2 reduction</a>

                  </li>
                  <li><a href="#">High quality ingredients</a></li>
                  <li><a href="#">Social responsibility</a></li>
                </ul>

              </div>
            </li>
          </ul>
        </nav>
        <div class="right-block">
          <span class="pta--deparatment">
            <a href="https://www.side-by-side.de/"> PTA department</a></span>

          <span class="pta--flag"><img src="../../assets/images/selector-de.png" alt="block__item--flag" width="20px"
              height="20px" />
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




.nav-item-arrow li a::after {

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
