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
    <div class="bg-white sm:-mx-10 md:mx-10 shadow-lg sm:p-3 rounded-xl">
      <p class="py-2 text-xl font-sans font-bold">Affected Countries</p>
      <TableCases
        :population="population"
        :affectedCountries="affectedCountries"
        :countries="countries"
      />
    </div>

    <div class="bg-white sm:-mx-10 md:mx-10 shadow-lg md:p-3 rounded-xl mt-7">
      <div class="row mt-5">
        <div class="col">
          <ChartCases :chartData="chartData" />
        </div>
      </div>
    </div>
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
      all: [],
      countries: [],
      totalcases: 0,
      active: 0,
      critical: 0,
      recovered: 0,
      deaths: 0,
      population: 0,
      affectedCountries: 0,
      chartData: [],
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
    axios
      .get("https://disease.sh/v3/covid-19/countries?sort=cases")
      .then((response) => {
        this.countries = response.data;
      });
  },

  async created() {
    this.chartData = await axios.get(
      "https://disease.sh/v3/covid-19/historical/all?lastdays=30"
    );
    this.chartData = this.chartData.data
  },
};
</script>
