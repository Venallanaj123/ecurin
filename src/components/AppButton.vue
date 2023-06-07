<template>
  <div class="btn-center">
    <a class="btn-center__global buttton" :href="link">{{ buttonText }}</a>
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

@media only screen and (max-width: 768px) {
  .btn-center {
    &__global {
      width: 100%;
      padding: 1.6rem 3.5rem;
    }
  }
}
</style>
