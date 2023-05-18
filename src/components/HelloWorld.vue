<template>
  <div>
    <button @click="isOpen = !isOpen">
      {{ isOpen ? "Close" : "Menu" }}
    </button>

    <ul class="menu__list nav-menu level-1" :class="{ open: isOpen }">
      <li class="menu__item">
        <a href="#">Products</a>
        <ul class="menu__subitem level-2">
          <li class="">
            <a href="" class="nested" @click.prevent="toggleActiveClass"
              >Product line</a
            >

            <transition name="slide-down">
              <ul v-if="isActive" class="menu__subnested level-3" @click.stop>
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
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  data() {
    return {
      isOpen: false,
      isActive: false,
    };
  },
  methods: {
    toggleActiveClass() {
      this.isActive = !this.isActive;
    },
  },
};
</script>

<style>
.menu__list {
  display: none;
}
.menu__list.open {
  display: block;
}
.slide-down-enter-active,
.slide-down-leave-active {
  transition: all 0.3s ease;
}
.slide-down-enter,
.slide-down-leave-to {
  transform: translateY(-10px);
  opacity: 0;
}
</style>
