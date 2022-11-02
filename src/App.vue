<script setup>
import { RouterLink, RouterView } from "vue-router";
import HelloWorld from "./components/HelloWorld.vue";
import Topwrapper from "./components/Topwrapper.vue";
import CardCases from "./components/CardCases.vue";
</script>

<template>
  <div>
    <div>
      <Topwrapper />
    </div>
    <div class="container w-full mx-auto pt-20">
      <div
        class="w-full px-4 md:px-0 md:mt-8 mb-16 text-gray-800 leading-normal"
      >
        <CardCases />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "app",
  components: { Topwrapper, CardCases },
};
</script>

<style scoped></style>
