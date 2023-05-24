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
@media only screen and (max-width: 768px) {
  .center-title {
    & h2 {
      font-size: 2.4rem;
      line-height: 2.8rem;
    }
  }
}
</style>
