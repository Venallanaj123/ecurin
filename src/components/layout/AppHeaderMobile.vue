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
          <ul class="nav-menu"></ul>
        </nav>

        <nav class="navbar-visible-desktop">
          <ul class="menu-first-level">
            <li
              class="menu-first-level__item"
              v-for="(item, index) in menuItems"
              :key="index"
              @mouseover="(e) => showSubmenuFirstLevel(e, item)"
              @mouseleave="(e) => hideSubmenu(e)"
            >
              <a :href="item.href">{{ item.title }}</a>
              <!-- v-if="item === selectedItem" -->
              <div class="wrap-subemenu">
                <ul id="submenu" class="menu-first-level__flyout">
                  <li
                    id="li"
                    class="menu-secondary-level__item center"
                    v-for="(subitem, subindex) in item.submenu"
                    :key="subindex"
                    @mouseover="(e) => showSubmenuSecondLevel(e, subitem)"
                    @mouseleave="(e) => hideSubmenu(e)"
                  >
                    <a :href="subitem.href">{{ subitem.title }}</a>

                    <ul class="menu-secondary-level__flyout submenu">
                      <li
                        class="menu-thirdy-level__item"
                        v-for="(nestedItem, nestedIndex) in subitem.nestedItems"
                        :key="nestedIndex"
                      >
                        <a :href="nestedItem.href">{{ nestedItem.title }}</a>
                      </li>
                    </ul>
                  </li>
                </ul>
              </div>
            </li>
          </ul>
        </nav>

        <div class="right-block">
          <span class="pta--deparatment">
            <a href="https://www.side-by-side.de/"> PTA department</a></span
          >

          <span class="pta--flag"
            ><img
              src="../../assets/images/selector-de.png"
              alt="block__item--flag"
              width="20px"
              height="20px"
            />
          </span>
          <span class="pta-language">EN</span>

          <span class="pta--search">
            <svg
              version="1.1"
              xmlns="http://www.w3.org/2000/svg"
              width="25"
              height="25"
              viewBox="0 0 32 32"
            >
              <path
                d="M13.455 2.182c6.226 0 11.273 5.047 11.273 11.273 0 2.851-1.058 5.454-2.803 7.439l7.483 7.485-1.029 1.029-7.485-7.483c-1.985 1.745-4.588 2.803-7.439 2.803-6.226 0-11.273-5.047-11.273-11.273s5.047-11.273 11.273-11.273zM13.455 3.636c-5.422 0-9.818 4.396-9.818 9.818s4.396 9.818 9.818 9.818c5.422 0 9.818-4.396 9.818-9.818s-4.396-9.818-9.818-9.818z"
              ></path>
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
          title: "Products",
          href: "https://www.eucerin.de/produkte",
          submenu: [
            {
              title: "product line ",
              href: "https://www.eucerin.de/produkte",
              nestedItems: [
                {
                  title: "Actinic Control",
                  href: "https://www.eucerin.de/produkte/actinic-control",
                },
                {
                  title: "anti pigment",
                  href: "https://www.eucerin.de/produkte/anti-pigment",
                },
                {
                  title: "Aquaphor Protect &amp; Repair",
                  href: "https://www.eucerin.de/produkte/actinic-control",
                },
                {
                  title: "Aquaporin Active",
                  href: "https://www.eucerin.de/produkte/anti-pigment",
                },
                {
                  title: "AtopiControl",
                  href: "https://www.eucerin.de/produkte/anti-pigment",
                },
                {
                  title: "deodorants and antiperspirants",
                  href: "https://www.eucerin.de/produkte/anti-pigment",
                },
                {
                  title: "DermatoCLEAN",
                  href: "https://www.eucerin.de/produkte/anti-pigment",
                },
                {
                  title: "DermoCapillaire",
                  href: "https://www.eucerin.de/produkte/dermocapillaire",
                },
                {
                  title: "DermoPure",
                  href: "https://www.eucerin.de/produkte/dermo-pure",
                },
                {
                  title: "Hyaluron-Filler + 3x EFFECT",
                  href: "https://www.eucerin.de/produkte/dermo-pure",
                },
                {
                  title: "Hyaluron-Filler + Elasticity",
                  href: "https://www.eucerin.de/produkte/dermo-pure",
                },
                {
                  title: "Hyaluron filler + urea",
                  href: "https://www.eucerin.de/produkte/dermo-pure",
                },
                {
                  title: "Hyaluron filler + volume lift",
                  href: "https://www.eucerin.de/produkte/dermo-pure",
                },
                {
                  title: "Lipo balance",
                  href: "https://www.eucerin.de/produkte/dermo-pure",
                },
                {
                  title: "pH5",
                  href: "https://www.eucerin.de/produkte/dermo-pure",
                },
                {
                  title: "Q10 Active",
                  href: "https://www.eucerin.de/produkte/dermo-pure",
                },
                {
                  title: "sun protection",
                  href: "https://www.eucerin.de/produkte/dermo-pure",
                },
                {
                  title: "UreaRepair",
                  href: "https://www.eucerin.de/produkte/dermo-pure",
                },
                {
                  title: "Ultra Sensitive",
                  href: "https://www.eucerin.de/produkte/dermo-pure",
                },
                {
                  title: "all products",
                  href: "https://www.eucerin.de/produkte/dermo-pure",
                },
              ],
            },
            // {
            //   title: "skin condition ",
            //   href: "https://www.eucerin.de/produkte",
            //   nestedItems: [
            //     {
            //       title: "anti age",
            //       href: "https://www.eucerin.de/produkte/anti-age",
            //     },
            //     {
            //       title: "Dry skin",
            //       href: "https://www.eucerin.de/produkte/trockene-haut",
            //     },
            //     {
            //       title: "itchy skin",
            //       href: "https://www.eucerin.de/produkte/trockene-haut",
            //     },
            //     {
            //       title: "Blemished skin",
            //       href: "https://www.eucerin.de/produkte/trockene-haut",
            //     },
            //     {
            //       title: "reddening of the face",
            //       href: "https://www.eucerin.de/produkte/trockene-haut",
            //     },
            //     {
            //       title: "Sensitive skin",
            //       href: "https://www.eucerin.de/produkte/trockene-haut",
            //     },
            //     {
            //       title: "scalp and hair",
            //       href: "https://www.eucerin.de/produkte/trockene-haut",
            //     },
            //     {
            //       title: "sun protection",
            //       href: "https://www.eucerin.de/produkte/trockene-haut",
            //     },
            //     {
            //       title: "Pigment spots &amp; hyperpigmentation",
            //       href: "https://www.eucerin.de/produkte/trockene-haut",
            //     },
            //     {
            //       title: "Sweat",
            //       href: "https://www.eucerin.de/produkte/trockene-haut",
            //     },
            //     {
            //       title: "diabetic skin",
            //       href: "https://www.eucerin.de/produkte/trockene-haut",
            //     },
            //     {
            //       title: "all products",
            //       href: "https://www.eucerin.de/produkte/trockene-haut",
            //     },
            //   ],
            // },
          ],
        },
        {
          title: "Advice",
          href: "https://www.eucerin.de/hautzustand",
          submenu: [
            {
              title: "skin condition",
              href: "https://www.eucerin.de/produkte",
            },
            {
              title: "useful information",
              href: "https://www.eucerin.de/produkte",
            },
          ],
        },
        {
          title: "Research",
          href: "https://www.eucerin.de/unsere-forschung/aus-der-forschung",
          submenu: [
            {
              title: "Science behind the product lines",
              href: "https://www.eucerin.de/unsere-forschung/aus-der-forschung",
            },
            {
              title: "About our research",
              href: "https://www.eucerin.de/unsere-forschung/forschungshintergrund",
            },
            {
              title: "Our ingredients",
              href: "https://www.eucerin.de/unsere-forschung/datenbank-fuer-inhaltsstoffe",
            },
          ],
        },
        {
          title: "Brand & More",
          href: "https://www.eucerin.de/ueber-eucerin/purpose",
          submenu: [
            {
              title: "Eucerin's purpose",
              href: "#1",
            },
            {
              title: "Anti-aging refill capsules",
              href: "#2",
            },
            {
              title: "Body care for dry skin",
              href: "#3",
            },
            {
              title: "mothers day promo",
              href: "#4",
            },
            {
              title: "#1 against pigment spots",
              href: "#5",
            },
            {
              title: "#MYSKINNOFILTER",
              href: "#6",
            },
            {
              title: "HYALURON-FILLER + ELASTICITY with a new formula",
              href: "#7",
            },
            {
              title: "Aquaphor Protect &amp; Repair",
              href: "#8",
            },
            {
              title: "skin cancer prevention",
              href: "#9",
            },
            {
              title: "UreaRepair skin trust",
              href: "#10",
            },
            {
              title: "Atopic dermatitis care",
              href: "#11",
            },
            {
              title: "social mission",
              href: "#12",
            },
            {
              title: "#generationEucerin",
              href: "#13",
            },
            {
              title: "women study",
              href: "#14",
            },
            {
              title: "Dermanostic",
              href: "#15",
            },
            {
              title: "loyalty program",
              href: "#16",
            },
            {
              title: "Anton",
              href: "#17",
            },
          ],
        },
        {
          title: "sustainability",
          href: "https://www.eucerin.de/nachhaltigkeit",

          submenu: [
            {
              title: "CO2 reduction ",
              href: "https://www.eucerin.de/nachhaltigkeit/co2-reduzierung",
            },
            {
              title: "High quality ingredients ",
              href: "https://www.eucerin.de/nachhaltigkeit/hochwertige-inhaltsstoffe",
            },
            {
              title: "Social responsibility",
              href: "https://www.eucerin.de/nachhaltigkeit/soziale-eingliederung",
            },
          ],
        },
      ],
      selectedItem: null,
    };
  },

  methods: {
    showSubmenuFirstLevel(e, item) {
      let target = e.target.parentElement;
      console.log("item", e.target.parentElement);
      target.classList.add("active");
      this.selectedItem = item;

      let submenu = document.getElementById("submenu");
      let itemHeight = document.getElementById("li").offsetHeight;

      //   const itemHeight = submenu.querySelector("li").offsetHeight;

      //   const numItems = submenu.querySelectorAll("li").length;

      //   const submenuHeight = numItems * itemHeight;
    },

    showSubmenuSecondLevel(e, subitem) {
      let target = e.target.parentElement;
      console.log("subitem", e.target.parentElement);
      target.classList.add("active");
      this.selectedItem = subitem;
    },

    hideSubmenu(e) {
      console.log("remove", e.target.parentElement);
      let target = e.target.parentElement;

      let children = Array.from(target.children);
      children.forEach((child) => {
        child.classList.remove("active");
      });
    },
  },
};
</script>

<style scoped lang="scss">
@import "../../assets/scss/layout/header";

ul .menu-first-level__item:hover .menu-first-level__flyout.submenu {
  display: block;
}

.menu-first-level {
  display: flex;
  justify-content: center;
  align-items: center;

  &__item {
    list-style: none;

    &.active .menu-first-level__flyout {
      height: 770px;
      opacity: 1;
      visibility: visible;
    }

    & a {
      color: $textcolor;
      padding: 10px;
      text-decoration: none;
      font-size: 1.6rem;
      line-height: 1.9rem;
    }
  }

  &__flyout {
    background-color: #fff;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.15);
    width: 100%;
    left: 0;
    position: absolute;
    transition: height 0.5s;
    height: 0px;
    opacity: 0;
    visibility: hidden;
    cursor: pointer;
    list-style: none;
    padding: 2rem 0;

    & li {
      padding: 0.5rem 0;
      cursor: pointer;
      & a {
        font-weight: 500;
        cursor: pointer;
      }
    }
  }
}

.center {
  width: 100%;
  padding: 2.5rem 0;
  margin: 0 auto;
  max-width: 140rem;
}

.menu-secondary-level__item {
  position: relative;
  list-style-type: none;
  & .menu-secondary-level__flyout {
    position: absolute;
    top: 0;
    left: 150px;
    list-style-type: none;
  }
  & .menu-thirdy-level__item {
    /*position: absolute;
    top: 10px;*/
    left: 150px;
  }
}
</style>
