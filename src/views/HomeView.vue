<script setup>
import axios from "axios";
import DataTitle from "../components/DataTitle.vue";
import CardCases from "../components/CardCases.vue";
import TableCases from "../components/TableCases.vue";
import ChartCases from "../components/ChartCases.vue";
</script>

<template class="bg-gray">
  <div class="home py-10">
    <DataTitle :totalcases="totalcases" />
    <CardCases
      :active="active"
      :critical="critical"
      :recovered="recovered"
      :deaths="deaths"
    />
    <div class="bg-white mx-10 shadow-lg p-3 rounded-xl">
      <p class="py-2 text-xl font-sans font-bold">Affected Countries</p>
      <TableCases
        :population="population"
        :affectedCountries="affectedCountries"
        :countries="countries"
      />
    </div>
    <ChartCases />
  </div>
</template>

<script>
export default {
  name: "HomeView",
  components: { DataTitle, CardCases, TableCases, ChartCases },
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
      countries: [],
      totalcases: 0,
      active: 0,
      critical: 0,
      recovered: 0,
      deaths: 0,
      population: 0,
      affectedCountries: 0,
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
        this.population = response.data.population;
        this.affectedCountries = response.data.affectedCountries;
      });
    axios.get("https://disease.sh/v3/covid-19/countries").then((response) => {
      this.countries = response.data;
    });
  },
};
</script>
