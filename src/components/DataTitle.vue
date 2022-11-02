<template>
  <div class="text-center">
    <h2 class="text-3xl font-bold">{{totalcases}}</h2>
    <h5 class="TotalCases">Total Cases</h5>
  </div>
</template>

<script>
export default {
  name: "DataTitle",
  components: {},
  props: ["totalcases"],
};
</script>
