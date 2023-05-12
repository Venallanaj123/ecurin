<template>
  <div class="center-title">
    <h2>{{ title }}</h2>
  </div>
</template>

<script>
export default {
  name: "AppTitle",
  props: {
    title: {
      type: String,
      required: true,
    },
  },
};
</script>

<style lang="scss">
.center-title {
  text-align: center;

  & h2 {
    @include subheading;
  }
}
</style>
