<template>
  <div>
    <h1>Your Cart</h1>
    <div class="products">
      <div v-for="(product, index) in cart" :key="index">
        <img :src="product.img" alt="product-image" />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "PreviewCart",
  props: ["cart"],
  data() {
    return {};
  },
  methods: {
 
  },
  mounted() {
    
  },
};
</script>

<style scoped>

</style>
