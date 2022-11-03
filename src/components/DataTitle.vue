<template>
  <div class="text-center">
    <!-- <h2 class="text-3xl font-bold">{{ totalcases }}</h2> -->
    <h2 class="text-3xl font-bold">
      <vue3-autocounter
        ref="counter"
        :startAmount="0"
        :endAmount="totalcases"
        :duration="2"
        separator=","
      />
    </h2>
    <h5 class="TotalCases">Total Cases</h5>
    <CardCases />
  </div>
</template>

<script>
import CardCases from "./CardCases.vue";
import Vue3autocounter from "vue3-autocounter";
export default {
  name: "DataTitle",
  components: {
    "vue3-autocounter": Vue3autocounter,
    CardCases
  },
  props: ["totalcases"],
};
</script>
