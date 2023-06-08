<template>
  <div>
    <AppNivea />
    <AppBackground />
  </div>
</template>
<script>
import AppNivea from "../components/nivea/AppNivea.vue";
import AppBackground from "@/components/nivea/AppBackground.vue";
export default {
  name: "NiveaView",
  components: {
      AppNivea,
    AppBackground,
  },
};
</script>
