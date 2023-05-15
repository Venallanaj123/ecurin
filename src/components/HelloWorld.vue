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
              ],
            },
          ],
        },
        {
          title: "Research",
          href: "https://www.eucerin.de/unsere-forschung/aus-der-forschung",
          submenu: [
            {
              title: "test",
              href: "#",
            },
            {
              title: "test2",
              href: "#",
            },
          ],
        },
        {
          title: "Brand and More",
          href: "https://www.eucerin.de/unsere-forschung/aus-der-forschung",
          submenu: [
            {
              title: "test3",
              href: "#",
            },
            {
              title: "test4",
              href: "#",
            },
          ],
        },
      ],

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

        //If there is no nestedItems
        if (nestedItems.length == 0) {
          nestedItems = document.querySelectorAll(
            ".menu-secondary-level__item"
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
  },
};
</script>

Take this code check line by line and costume that to calculate also the height
of the submenu, which doesn't have the subitems into it but calcaulate only the
submenu such as menu Research, Brand & More.
Make it dynamic
