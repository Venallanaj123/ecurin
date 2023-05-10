<template>
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
          <a :href="subitem.href" class="arrow right">{{ subitem.title }}</a>

          <ul
            class="menu-secondary-level__flyout active submenu"
            v-if="selectedSubmenuItem === subitem"
            ref="submenu"
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
</template>

<script>
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
              ],
            },
          ],
        },
      ],

      selectedItem: null,
      selectedSubmenuItem: null,
    };
  },

  methods: {
    showSubmenuFirstLevel(e, item) {
      let target = e.target.parentElement;
      console.log("item", target, "selected item", item);
      target.classList.add("active");
      this.selectedItem = item;

      if (this.selectedSubmenuItem == null)
        this.selectedSubmenuItem = item.submenu[0];
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
      console.log("subitem", subitem, target, subitem);
    },

    hideSubmenuSecondLevel(e, subitem) {
      let target = e.target.parentElement;
      target.classList.remove("active");
      if (this.selectedSubmenuItem === subitem) {
        this.selectedSubmenuItem = null;
      }
    },

    getSubMenuHeight(parentIndex) {
      return this.$refs.submenu[parentIndex].scrollHeight;
    },
  },
};
</script>
