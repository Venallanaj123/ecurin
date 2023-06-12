<template>
  <div v-bind:class="{ active: isActive }">
    <p>Some content</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isActive: false,
    };
  },
};
</script>
