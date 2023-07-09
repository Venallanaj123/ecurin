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
              <li
                class="menu__item"
                v-for="(menuItem, index) in menuItems"
                :key="index"
              >
                <a v-if="!showSubmenu" :href="menuItem.href">{{
                  menuItem.title
                }}</a>
                <a v-if="showSubmenu" :href="menuItem.href"
                  >{{ subItemsShown.title }}
                  <li><button @click="back()">back</button></li>
                </a>

                <ul class="menu__subitem level-2">
                  <li
                    v-for="(subitemItem, index) in menuItem.subitemItems"
                    :key="index"
                  >
                    <a
                      v-if="!showSubmenu"
                      :href="subitemItem.href"
                      class="nested"
                      @click.prevent="
                        showChildrenMobile(
                          subitemItem.title,
                          menuItem.subitemItems
                        )
                      "
                      >{{ subitemItem.title }}</a
                    >
                  </li>
                </ul>

                <transition name="slide-fade">
                  <ul v-if="showSubmenu" class="menu__subitem level-2">
                    <li
                      v-for="(
                        subnestedItem, index
                      ) in subItemsShown.subnestedItems"
                      :key="index"
                    >
                      <a class="" :href="subnestedItem.href">{{
                        subnestedItem.title
                      }}</a>
                    </li>
                  </ul>
                </transition>
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
          title: "Products",
          href: "https://www.eucerin.de/produkte",
          subitemItems: [
            {
              title: "Product line",
              href: "https://www.eucerin.de/produkte",
              subnestedItems: [
                {
                  title: "Actinic Control",
                  href: "https://www.eucerin.de/produkte/actinic-control",
                },
                {
                  title: "anti pigment",
                  href: "https://www.eucerin.de/produkte/anti-pigment",
                },
              ],
            },
            {
              title: "Skin Condition",
              subnestedItems: [
                {
                  title: "anti age",
                  href: "https://www.eucerin.de/produkte/anti-age",
                },
                {
                  title: "Dry skin",
                  href: "https://www.eucerin.de/produkte/trockene-haut",
                },
              ],
            },
          ],
        },
      ],

      showSubmenu: false,
      subItemsShown: null,
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
      if (this.showSubmenu) this.showSubmenu = false;
    },
    showChildrenMobile(titleMenu, subItems) {
      this.subItemsShown = subItems.filter((x) => x.title == titleMenu)[0];

      this.showSubmenu = true;
    },
    back() {
      this.showSubmenu = false;
    },
  },
};
</script>
