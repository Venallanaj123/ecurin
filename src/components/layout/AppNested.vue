<template>
  <div class="MenuPanel">
    <div
      class="Menu__panel"
      :class="{ transition: isTranslating }"
      :style="[positionStyle]"
    >
      <div v-if="list.title" @click="handleHeaderClicked" class="Menu__header">
        <span v-show="showHeaderArrow" class="arrow">
          <LeftArrowIcon />
        </span>
        {{ list.title }}
      </div>

      <ul class="Menu__list">
        <li
          v-for="(item, index) in list.children"
          @click="handleItemClicked(item)"
          :key="index"
          class="Menu__item"
        >
          <template v-if="item.children.length > 0" :href="item.link">
            <div class="text">{{ item.title }}</div>
            <span class="arrow">
              <RightArrowIcon />
            </span>
          </template>
          <a v-else :href="item.link">
            <div class="text">{{ item.title }}</div>
          </a>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
import RightArrow from "../icons/RightArrow.vue";
import LeftArrow from "../icons/LeftArrow.vue";
export default {
  name: "AppNested",
    components:
    {
        RightArrow,
        LeftArrow
    },
  data() {
    return {
      menuItems: [],
    };
  },
};
</script>
