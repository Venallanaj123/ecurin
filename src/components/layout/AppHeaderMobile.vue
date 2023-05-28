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
            <!-- <ul class="menu__list nav-menu level-1">
              <li class="menu__item"  v-for="menu in menuItems" :key="menu.id>
            <a :href="menu.href">{{ menu.href }}</a>
              
              </li>
            </ul> -->
            <ul class="menu__list nav-menu level-1">
              <li class="menu__item">
                <a href="#">Products</a>
                <ul class="menu__subitem level-2">
                  <li class="">
                    <a
                      href="#"
                      class="nested"
                      @click.prevent="showChildrenMobile()"
                      >Product line</a
                    >

                    <transition name="slide-fade">
                      <ul v-if="showSubmenu" class="menu__subnested level-3">
                        <li><a href="#">Actinic alcolh</a></li>
                        <li><a href="#">Actinic alcolh</a></li>
                        <li><a href="#">Actinic alcolh</a></li>
                      </ul>
                    </transition>
                  </li>
                  <li>
                    <a href="" class="nested">Skin Condition</a>
                  </li>
                </ul>
              </li>
            </ul>

            <!-- <ul class="menu__list nav-menu level-1">
              <li
                class="menu__item"
                v-for="(menu, index) in menuItems"
                :key="index"
              >
                <a :href="menu.href" class="nested">{{ menu.title }}</a>

                <ul class="menu__subitem level-2">
                  <li
                    class=""
                    v-for="(subitem, index) in subitemItems"
                    :key="index"
                  >
                    <a
                      :href="subitem.href"
                      class="nested"
                      @click.prevent="showChildrenMobile()"
                      >{{ subitem.title }}</a
                    >

                    <transition name="slide-fade">
                      <ul v-if="showSubmenu" class="menu__subnested level-3">
                        <li><a href="#">Actinic alcolh</a></li>
                        <li><a href="#">Actinic alcolh</a></li>
                        <li><a href="#">Actinic alcolh</a></li>
                      </ul>
                    </transition>
                  </li>
                </ul>
              </li>
            </ul> -->
          </nav>
        </div>
      </div>
    </div>
  </header>
</template>

<style lang="scss">
@import "../../assets/scss/layout/headerMobile";

.slide-fade-enter-active,
.slide-fade-leave-active {
  transition: all 0.5s ease;
}

.slide-fade-enter,
.slide-fade-leave-to {
  transform: translateX(100%);
  opacity: 0;
}
</style>
<script>
export default {
  name: "AppHeaderMobile",

  data() {
    return {
      menuItems: [
        {
          title: " Product  ",
          subitemItems: [
            {
              title: "test,",
            },
            {
              title: "test2,",
            },
          ],
        },
        {
          title: " Skin Condition ",
        },
      ],
      showSubmenu: false,
    };
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
    showChildrenMobile() {
      this.showSubmenu = !this.showSubmenu;
    },
  },
};
</script>
