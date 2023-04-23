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
  @include heading;
  text-align: center;
  & h2 {
    font-size: 2.4rem;
    line-height: 2.9rem;
  }
}
</style>
