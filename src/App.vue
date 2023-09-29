<script setup>
import { RouterView } from "vue-router";
import Topwrapper from "./components/Topwrapper.vue";
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
  components: { Topwrapper },
};
</script>
