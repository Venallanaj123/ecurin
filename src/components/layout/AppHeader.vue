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
            <!-- <li><a href="@">test</a></li> -->
          </ul>
        </nav>

        <nav class="navbar-visible-desktop">
          <ul class="navbar-first-level">
            <li
              v-for="(item, index) in menuItems"
              :key="index"
              class="navbar-first-level__item"
            >
              <a href="#">{{ item.label }}</a>

              <!-- Separate the submenu items into separate ul elements -->

              <ul
                :id="'submenu-' + index"
                class="navbar-first-level__flyout submenu"
              >
                <li
                  v-for="(childItem, childIndex) in item.children"
                  :key="childIndex"
                  class="navbar-first-level__item"
                >
                  <a href="#">{{ childItem.label }}</a>
                </li>
              </ul>

              <!-- Add another ul element for the second set of submenu items -->
              <ul
                :id="'submenu2-' + index"
                class="navbar-first-level__flyout submenu"
              >
                <li
                  v-for="(childItem, childIndex) in item.children"
                  :key="childIndex"
                  class="navbar-secondary-level__item"
                >
                  <a
                    href="#"
                    @mouseover="showSubSubmenu(index, childIndex)"
                    @mouseout="hideSubSubmenu(index, childIndex)"
                    >{{ childItem.label }}</a
                  >
                  <ul
                    class="nested-submenu"
                    :id="'nested-submenu-' + index + '-' + childIndex"
                  >
                    <li
                      v-for="(
                        nestedChildItem, nestedChildIndex
                      ) in childItem.children"
                      :key="nestedChildIndex"
                    >
                      <a href="#">{{ nestedChildItem.label }}</a>
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
          label: "Menu Item 1",
          children: [
            {
              label: "Submenu Item 1",
              children: [
                {
                  label: "Nested Submenu Item 1",
                },
                {
                  label: "Nested Submenu Item 2",
                },
                {
                  label: "Nested Submenu Item 3",
                },
                {
                  label: "Nested Submenu Item 4",
                },
              ],
            },
            {
              label: "Submenu Item 2",
              children: [
                {
                  label: "Nested Submenu Item 3",
                },
                {
                  label: "Nested Submenu Item 4",
                },
              ],
            },
            {
              label: "test",
            },
            {
              label: "test",
            },
          ],
        },
        {
          label: "Menu Item 2",
          children: [
            {
              label: "Submenu Item 2",
              children: [
                {
                  label: "Nested Submenu Item 3",
                },
                {
                  label: "Nested Submenu Item 4",
                },
                {
                  label: "Nested Submenu Item 3",
                },
                {
                  label: "Nested Submenu Item 4",
                },
              ],
            },
          ],
        },
      ],
    };
  },

  methods: {
    showSubmenu(submenuId) {
      const submenu = document.getElementById(submenuId);
      // Get the height of a single list item
      const itemHeight = submenu.querySelector("li").offsetHeight;
      // Get the number of list items in the submenu
      const numItems = submenu.querySelectorAll("li").length;
      // Calculate the height of the submenu
      const submenuHeight = numItems * itemHeight;
      // Set the height of the submenu
      //submenu.style.height = `${submenuHeight}px`; //Hiqe komentin
      // Display the submenu
      //submenu.style.display = "block";
    },

    hideSubmenu(submenuId) {
      document.getElementById(submenuId).style.display = "none";
    },
    showSubSubmenu(submenuId, childIndex) {
      const subsubmenu = document.getElementById(
        `nested-submenu-${submenuId}-${childIndex}`
      );

      subsubmenu.style.display = "block";
    },

    hideSubSubmenu(submenuId, childIndex) {
      // Get the sub-submenu element
      const subsubmenu = document.getElementById(
        `nested-submenu-${submenuId}-${childIndex}`
      );
      // Hide the sub-submenu
      subsubmenu.style.display = "none";
    },
  },
};
</script>

<style scoped lang="scss">
@import "../../assets/scss/layout/header";

/* Start to style na-menu for mobile */

.navbar-first-level__flyout {
  display: none;
}

.navbar-first-level__flyout {
  background-color: #e8eaeb;
  width: 100%;
  /*display: flex;
  flex-direction: column;
  justify-content: space-between;*/
  align-items: stretch;
  left: 0;
  position: absolute;

  & li {
    /* display: flex;*/
    list-style: none;
  }
}

/* Add this CSS rule to hide the submenus by default */
.navbar-first-level__flyout.submenu {
  display: none;
}

ul {
  display: flex;
  justify-content: center;
  align-items: center;

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

/* Use the :hover pseudo-class to show the submenu when hovering over the main menu item */
ul .navbar-first-level__item:hover .navbar-first-level__flyout.submenu {
  display: block;
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

.nested-submenu {
  display: none;
}
.navbar-secondary-level__item:hover .nested-submenu {
  display: block;
}
</style>
