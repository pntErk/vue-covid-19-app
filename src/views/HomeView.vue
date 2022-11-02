<script setup>
import axios from "axios";
import DataTitle from "../components/DataTitle.vue";
</script>

<template>
  <div class="home">
    <DataTitle :totalcases="totalcases" />
  </div>
</template>

<script>
export default {
  name: "HomeView",
  components: { DataTitle },
  data() {
    return {
      delay: 1000,
      options: {
        useEasing: true,
        useGrouping: true,
        separator: ",",
        decimal: ".",
        prefix: "",
        suffix: "",
      },
      totalcases: 0,
    };
  },
  mounted() {
    axios
      .get("https://disease.sh/v3/covid-19/all?yesterday=true&allowNull=true")
      .then((response) => (this.totalcases = response.data.cases));
  },
};
</script>
