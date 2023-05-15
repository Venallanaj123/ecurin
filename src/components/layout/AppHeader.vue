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
          <ul class="nav-menu level-1">
            <li>
              <a href="" class="nested">Categories </a>
              <ul class="sub-menu level-2">
                <li>
                  <a href="" class="nested">Living Room </a>
                </li>
                <li><a href="" class="nested">Living Room </a></li>
                <li><a href="" class="nested">Living Room </a></li>
              </ul>
            </li>
          </ul>
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

              <ul class="menu-first-level__flyout">
                <li
                  class="menu-secondary-level__item center"
                  v-for="(subitem, subindex) in item.submenu"
                  :key="subindex"
                  :class="{ active: selectedItem === subitem }"
                  @mouseover="(e) => showSubmenuSecondLevel(e, subitem)"
                  @mouseleave="(e) => hideSubmenuSecondLevel(e, subitem)"
                >
                  <a :href="subitem.href" class="arrow right"
                    >{{ subitem.title }}
                  </a>

                  <ul
                    class="menu-secondary-level__flyout active submenu"
                    v-if="selectedSubmenuItem === subitem"
                  >
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

      <!-- <header class="page-header">
        <nav>
          <div class="header-bar">
            <button class="toggle-menu" type="button">MENU</button>
            <a href="" class="brand">BRAND</a>
            <a href="" class="social" target="_blank" title="">
              <svg
                xmlns="http://www.w3.org/2000/svg"
                width="24"
                height="24"
                viewBox="0 0 24 24"
              >
                <path
                  d="M24 4.557c-.883.392-1.832.656-2.828.775 1.017-.609 1.798-1.574 2.165-2.724-.951.564-2.005.974-3.127 1.195-.897-.957-2.178-1.555-3.594-1.555-3.179 0-5.515 2.966-4.797 6.045-4.091-.205-7.719-2.165-10.148-5.144-1.29 2.213-.669 5.108 1.523 6.574-.806-.026-1.566-.247-2.229-.616-.054 2.281 1.581 4.415 3.949 4.89-.693.188-1.452.232-2.224.084.626 1.956 2.444 3.379 4.6 3.419-2.07 1.623-4.678 2.348-7.29 2.04 2.179 1.397 4.768 2.212 7.548 2.212 9.142 0 14.307-7.721 13.995-14.646.962-.695 1.797-1.562 2.457-2.549z"
                />
              </svg>
            </a>
          </div>
          <div class="list-wraper">
            <ul>
              <li><a href="">test</a></li>
              <li><a href="">test</a></li>
              <li><a href="">test</a></li>
              <li><a href="">test</a></li>
            </ul>
          </div>
        </nav>
      </header> -->
    </div>
  </header>
</template>

<script>
import VueNestedMenu from "vue-nested-menu";

export default {
  name: "AppHeader",
  components: { VueNestedMenu },
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
            {
              title: "skin condition ",
              href: "https://www.eucerin.de/produkte",
              nestedItems: [
                {
                  title: "anti age",
                  href: "https://www.eucerin.de/produkte/anti-age",
                },
                {
                  title: "Dry skin",
                  href: "https://www.eucerin.de/produkte/trockene-haut",
                },
                {
                  title: "itchy skin",
                  href: "https://www.eucerin.de/produkte/trockene-haut",
                },
                {
                  title: "Blemished skin",
                  href: "https://www.eucerin.de/produkte/trockene-haut",
                },
                {
                  title: "reddening of the face",
                  href: "https://www.eucerin.de/produkte/trockene-haut",
                },
                {
                  title: "Sensitive skin",
                  href: "https://www.eucerin.de/produkte/trockene-haut",
                },
                {
                  title: "scalp and hair",
                  href: "https://www.eucerin.de/produkte/trockene-haut",
                },
                {
                  title: "sun protection",
                  href: "https://www.eucerin.de/produkte/trockene-haut",
                },
                {
                  title: "Pigment spots &amp; hyperpigmentation",
                  href: "https://www.eucerin.de/produkte/trockene-haut",
                },
                {
                  title: "Sweat",
                  href: "https://www.eucerin.de/produkte/trockene-haut",
                },
                {
                  title: "diabetic skin",
                  href: "https://www.eucerin.de/produkte/trockene-haut",
                },
                {
                  title: "all products",
                  href: "https://www.eucerin.de/produkte/trockene-haut",
                },
              ],
            },
          ],
        },
        {
          title: "Advice",
          href: "https://www.eucerin.de/hautzustand",
          submenu: [
            {
              title: "skin condition",
              href: "https://www.eucerin.de/produkte",

              nestedItems: [
                {
                  title: "anti age",
                  href: "https://www.eucerin.de/hautzustand/anti-age",
                },
                {
                  title: "Dry skin",
                  href: "https://www.eucerin.de/hautzustand/trockene-haut",
                },
                {
                  title: "neurodermatitis",
                  href: "https://www.eucerin.de/hautzustand/neurodermitis",
                },
                {
                  title: "Blemished skin",
                  href: "https://www.eucerin.de/hautzustand/unreine-haut",
                },
                {
                  title: "reddening of the face",
                  href: "https://www.eucerin.de/hautzustand/roetungen-im-gesicht",
                },
                {
                  title: "Sensitive skin",
                  href: "https://www.eucerin.de/hautzustand/roetungen-im-gesicht",
                },
                {
                  title: "sun protection",
                  href: "https://www.eucerin.de/hautzustand/roetungen-im-gesicht",
                },
                {
                  title: "Pigment spots &amp; hyperpigmentation",
                  href: "https://www.eucerin.de/hautzustand/roetungen-im-gesicht",
                },
                {
                  title: "Sweating &amp; deodorant intolerance",
                  href: "https://www.eucerin.de/hautzustand/roetungen-im-gesicht",
                },
                {
                  title: "diabetic skin",
                  href: "https://www.eucerin.de/hautzustand/roetungen-im-gesicht",
                },
                {
                  title: "all articles",
                  href: "https://www.eucerin.de/hautzustand/roetungen-im-gesicht",
                },
              ],
            },
            {
              title: "useful information",
              href: "https://www.eucerin.de/produkte",

              nestedItems: [
                {
                  title: "skin knowledge",
                  href: "https://www.eucerin.de/beratung/die-haut-grundlagen",
                },
                {
                  title: "skin care",
                  href: "https://www.eucerin.de/beratung/hautbehandlung",
                },
                {
                  title: "skin indications",
                  href: "https://www.eucerin.de/beratung/hautprobleme",
                },
                {
                  title: "all articles",
                  href: "https://www.eucerin.de/hautzustand",
                },
              ],
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
              nestedItems: [
                {
                  title: "Sustainable packaging",
                  href: "https://www.eucerin.de/nachhaltigkeit/co2-reduzierung/nachhaltige-verpackung",
                },
                {
                  title: "climate protection",
                  href: "https://www.eucerin.de/nachhaltigkeit/co2-reduzierung/klimaschutz",
                },
                {
                  title: "sustainable production",
                  href: "https://www.eucerin.de/nachhaltigkeit/co2-reduzierung/nachhaltige-produktion",
                },
              ],
            },
            {
              title: "High quality ingredients ",
              href: "https://www.eucerin.de/nachhaltigkeit/hochwertige-inhaltsstoffe",
              nestedItems: [
                {
                  title: "Sustainable palm oil cultivation",
                  href: "https://www.eucerin.de/nachhaltigkeit/hochwertige-inhaltsstoffe/nachhaltiger-palmoel-anbau",
                },
                {
                  title: "Cosmetics without animal testing",
                  href: "https://www.eucerin.de/nachhaltigkeit/hochwertige-inhaltsstoffe/kosmetik-ohne-tierversuche",
                },
                {
                  title: "Cosmetics without microplastics",
                  href: "https://www.eucerin.de/nachhaltigkeit/hochwertige-inhaltsstoffe/kosmetik-ohne-mikroplastik",
                },
              ],
            },
            {
              title: "Social responsibility",
              href: "https://www.eucerin.de/nachhaltigkeit/soziale-eingliederung",
            },
          ],
        },
      ],
      menu: {
        title: "首頁",
        children: [
          {
            title: `Today's Deals`,
            link: `/today`,
            children: [],
          },
          {
            title: `Shop By Department`,
            children: [
              {
                title: `Amazon Music`,
                link: `/music`,
                children: [],
              },
              {
                title: `CDs and Vinyl`,
                link: `/cds`,
                children: [],
              },
            ],
          },
        ],
      },
      selectedItem: null,
      selectedSubmenuItem: null,
    };
  },

  methods: {
    automaticHeightMenu() {
      const flyout = document.querySelector(
        ".active .menu-first-level__flyout"
      );
      console.log(flyout, "flyout");

      if (flyout) {
        let nestedItems = document.querySelectorAll(".menu-thirdy-level__item");

        //If there is nestedItems
        if (nestedItems.length == 0) {
          nestedItems = document.querySelectorAll(
            ".menu-secondary-level__item "
          );
        }
        console.log(nestedItems, "nestedItems");

        // Calculate the total height of the nested items
        let nestedItemsHeight = 0;
        console.log(nestedItemsHeight, "nestedItemsHeight");

        nestedItems.forEach((item) => {
          nestedItemsHeight += item.offsetHeight;
        });

        // Set the height of the flyout to the total height of the nested items
        flyout.style.height = `${nestedItemsHeight}px`;
      }
    },
    showSubmenuFirstLevel(e, item) {
      let target = e.target.parentElement;
      console.log("item", target, "selected item", item);
      target.classList.add("active");
      this.selectedItem = item;

      if (this.selectedSubmenuItem == null)
        this.selectedSubmenuItem = item.submenu[0];

      setTimeout(() => this.automaticHeightMenu(), 100);
    },

    hideSubmenu(e) {
      console.log("remove", e.target.parentElement);
      let target = e.target.parentElement;

      let children = Array.from(target.children);
      children.forEach((child) => {
        child.classList.remove("active");
      });

      this.selectedSubmenuItem = null;
    },

    showSubmenuSecondLevel(e, subitem) {
      let target = e.target.parentElement;
      target.classList.add("active");
      this.selectedSubmenuItem = subitem;
    },
    hideSubmenuSecondLevel(e, subitem) {
      let target = e.target.parentElement;
      target.classList.remove("active");
      if (this.selectedSubmenuItem === subitem) {
        this.selectedSubmenuItem = null;
      }
    },

    /* Write code for mobile menu*/
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

.menu-secondary-level__item {
  flex-shrink: 0;
  -webkit-box-flex: 0;
  flex-grow: 0;
  flex-basis: calc(25% - 20px);
  max-width: calc(25% - 20px);
  margin-right: 10px;
  margin-left: 0;
}
.menu-secondary-level__flyout {
  position: absolute;
  margin-left: 10px;
  right: 0px;
  margin-right: 0px;
  min-height: 100%;
  max-width: 100%;
  width: calc(75% - 25px);
  padding-bottom: 40px;
  top: 0px;
  list-style-type: none;
}

.menu-first-level {
  display: flex;
  justify-content: center;
  align-items: center;

  &__item {
    list-style: none;

    &.active .menu-first-level__flyout {
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

    & li {
      padding: 0.5rem 0;
      cursor: pointer;
      list-style-type: none;
    }
    & a {
      font-weight: 500;
      cursor: pointer;
    }
    & .arrow::after {
      /* transform: rotate(-45deg);
      -webkit-transform: rotate(-45deg);
      border: solid $danger;
      border-width: 0 2px 2px 0;
      display: inline-block;
      padding: 3px;
      content: "";*/
    }
  }
}

.center {
  width: 100%;
  padding: 2.5rem 0;
  margin: 0 auto;
  max-width: 140rem;
}

.Menu__header {
  display: flex;
  align-items: center;
  padding-left: 35px;
  height: 50px;
  color: #fff;
  font-size: 16px;
  background-color: #232f3e;
  cursor: pointer;

  .arrow {
    padding-top: 2px;
    fill: #fff;
    margin-right: 10px;
    width: 10px;
    height: 100%;
    display: flex;
    align-items: center;
  }
}

.Menu__list {
  list-style: none;
  padding-bottom: 2px;

  .separator {
    border-bottom: 1px solid #d5dbdb;
    padding: 2px 0 0 0;
    margin: 0;
  }
}

.Menu__item {
  color: #4a4a4a;
  padding-left: 35px;
  height: 45px;
  display: flex;
  align-items: center;
  cursor: pointer;

  a {
    color: #4a4a4a;
    text-decoration: none;
  }

  .arrow {
    padding-top: 2px;
    padding-left: 15px;
    display: flex;
    align-items: center;
    width: 10px;
    height: 100%;
  }
}
</style>
