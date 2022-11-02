<script setup>
import { RouterLink, RouterView } from "vue-router";
import Topwrapper from "./components/Topwrapper.vue";
import CardCases from "./components/CardCases.vue";
</script>

<template>
  <Topwrapper />
  <div class="container">
    <router-view />
  </div>
</template>

<script>
export default {
  name: "app",
  components: { Topwrapper, CardCases },
};
</script>

<style scoped></style>
