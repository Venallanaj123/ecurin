<template>
  <header>
    <div class="container">
      <div class="header">
        <div class="menu-visible-mobile">
          <nav class="menu">
            <div class="menu__burger hamburger" @click="showMenuMobile()">
              <span class="bar"></span>
              <span class="bar"></span>
              <span class="bar"></span>
            </div>
            <div class="menu__logo">
              <img src="../../assets/images/logo.svg" alt="Logo" />
            </div>
            <ul class="menu__list nav-menu level-1">
              <li class="menu__item">
                <a href="#">Products</a>
                <ul class="menu__subitem level-2">
                  <li class="">
                    <a href="" class="nested" @click="showChildrenMobile()"
                      >Product line</a
                    >

                    <ul class="menu__subnested level-3">
                      <li><a href="#">Actinic alcolh</a></li>
                      <li><a href="#">Actinic alcolh</a></li>
                      <li><a href="#">Actinic alcolh</a></li>
                    </ul>
                  </li>
                  <li>
                    <a href="" class="nested">Skin Condition</a>
                  </li>
                </ul>
              </li>
            </ul>
          </nav>
        </div>
      </div>
    </div>
  </header>
</template>

<style lang="scss">
@import "../../assets/scss/layout/headerMobile";
</style>
<script>
export default {
  name: "AppHeaderMobile",

  data() {
    return {};
  },

  /* Write code for mobile menu*/
  methods: {
    showMenuMobile() {
      let showMenuMobile;
      let hamburger = document.querySelector(".hamburger");
      let navMenu = document.querySelector(".nav-menu");

      hamburger.addEventListener("click", showMenuMobile);
      hamburger.classList.toggle("active");
      navMenu.classList.toggle("active");
    },

    /* showChildrenMobile() {
      let showChildrenMobile;
      let nested = document.querySelector(".nested");
      let subnested = document.querySelector(".level-3");
      nested.addEventListener("click", showChildrenMobile);
      nested.classList.toggle("active");
      subnested.classList.toggle("active");
    },*/

    showChildrenMobile() {
        let showChildrenMobile;
         let nested = document.querySelector(".nested");
      let menuNested = document.querySelector(".menu__subnested");

      nested.addEventListener("click", showChildrenMobile);
      menuNested.classList.toggle("active");
    },
  },
};
</script>
