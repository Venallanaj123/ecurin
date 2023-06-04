<template>
  <div>
    <!-- <AppNivea /> -->
    <TestSlider />
    <!-- <SliderHooper /> -->
  </div>
</template>
<script>
// @ is an alias to /src
// import AppNivea from "../components/nivea/AppNivea.vue";
import TestSlider from "../components/nivea/TestSlider.vue";
// import SliderHooper from "@/components/nivea/SliderHooper.vue";

export default {
  name: "NiveaView",
  components: {
    TestSlider,
    // SliderHooper,
  },
};
</script>
