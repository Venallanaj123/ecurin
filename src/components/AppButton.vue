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
  },
};
</script>

<style scoped lang="scss">
.btn-center {
  display: flex;
  justify-content: center;
  margin-top: 1.7rem;
  &__global {
    @include btngrey;
    &:hover {
      background-color: $grey-btnhover;
    }
  }
}
</style>
