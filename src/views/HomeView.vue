<script setup>
import axios from "axios";
import DataTitle from "../components/DataTitle.vue";
import CardCases from "../components/CardCases.vue";
</script>

<template>
  <div class="home">
    <DataTitle :totalcases="totalcases" />
    <CardCases
      :active="active"
      :critical="critical"
      :recovered="recovered"
      :deaths="deaths"
    />
  </div>
</template>

<script>
export default {
  name: "HomeView",
  components: { DataTitle, CardCases },
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
      data: {},
      totalcases: 0,
      active: 0,
      critical: 0,
      recovered: 0,
      deaths: 0,
    };
  },
  mounted() {
    axios
      .get("https://disease.sh/v3/covid-19/all?yesterday=true&allowNull=true")
      .then((response) => {
        this.totalcases = response.data.cases;
        this.active = response.data.active;
        this.critical = response.data.critical;
        this.recovered = response.data.recovered;
        this.deaths = response.data.deaths;
      });
  },
};
</script>
