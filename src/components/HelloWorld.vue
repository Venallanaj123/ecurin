<template>
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
          <ul class="menu-first-level__flyout">
            <li
              class="menu-secondary-level__item center"
              v-for="(subitem, subindex) in item.submenu"
              :key="subindex"
            >
              <a :href="subitem.href" class="arrow right"
                >{{ subitem.title }}
              </a>

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
                                    title: "anti pigment",
                                    href: "https://www.eucerin.de/produkte/anti-pigment",
                                },
                                {
                                    title: "Aquaphor Protect &amp; Repair",
                                    href: "https://www.eucerin.de/produkte/actinic-control",
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
                               
                            ],
                        },
                    ],
                },
            ]
        }
    },
      methods: {
        showSubmenuFirstLevel(e, item) {
            let target = e.target.parentElement;
            console.log("item", e.target.parentElement);
            target.classList.add("active");
            this.selectedItem = item;

            let submenu = document.getElementById("submenu");
          
        },

        hideSubmenu(e) {
            console.log("remove", e.target.parentElement);
            let target = e.target.parentElement;

            let children = Array.from(target.children);
            children.forEach((child) => {
                child.classList.remove("active");
            });
        },
    }
    
};
