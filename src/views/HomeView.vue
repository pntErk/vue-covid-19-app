<script setup>
import api from "@/Api";
import ICountUp from "vue-countup-v2";
</script>

<template>
  <div class="home">
    <h3 class="overall_cases"><ICountUp :endVal="parseInt(totalcases)" /></h3>
    <h5 class="overall_cases_title">Total Cases</h5>
  </div>
</template>

<script>
export default {
  name: "HomeView",
  components: { ICountUp },
};
</script>
