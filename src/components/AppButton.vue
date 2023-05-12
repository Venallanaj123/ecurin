<template>
  <div class="btn-center">
    <a class="btn-center__global" :href="link">{{ buttonText }}</a>
  </div>
</template>

<script>
export default {
  name: "AppButton",
  props: {
    link: {
      type: String,
      required: true,
    },
    buttonText: {
      type: String,
      required: true,
    },
    href: {
      link: "#",
    },
  },
};
</script>

<style scoped lang="scss">
.btn-center {
  display: flex;
  justify-content: center;
 
  &__global {
    @include btngrey;
    &:hover {
      background-color: $grey-btnhover;
    }
  }
}
</style>
