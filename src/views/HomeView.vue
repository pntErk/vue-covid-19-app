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
      <TableCases
        :population="population"
        :affectedCountries="affectedCountries"
        :countries="countries"
      />
    </div>

    <div class="bg-white sm:-mx-10 md:mx-10 shadow-lg md:p-3 rounded-xl mt-7">
      <div class="row">
        <div class="col">
          <p class="py-2 font-sans font-bold sm:text-base md:lg:text-xl">
            Records in 30 Days
          </p>

          <p class="mb-3 sm:text-sm md:lg:text-base sm:-mt-3">
            (Covid-19 data sourced from Johns Hopkins University, updated every
            10 minutes)
          </p>
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
      countries: [],
      chartData: [],
      totalcases: 0,
      active: 0,
      critical: 0,
      recovered: 0,
      deaths: 0,
      population: 0,
      affectedCountries: 0,
    };
  },
  created() {
    this.getAllCases();
    this.getCountries();
    this.getChartData(30);
  },
  methods: {
    async getChartData(day) {
      this.chartData = await axios.get(
        "https://disease.sh/v3/covid-19/historical/all?lastdays=" + day + ""
      );
      this.chartData = this.chartData.data;
    },
    async getAllCases() {
      await axios
        .get(
          "https://disease.sh/v3/covid-19/all?yesterday=false&allowNull=true"
        )
        .then((response) => {
          this.totalcases = response.data.cases;
          this.active = response.data.active;
          this.critical = response.data.critical;
          this.recovered = response.data.recovered;
          this.deaths = response.data.deaths;
          this.population = response.data.population;
          this.affectedCountries = response.data.affectedCountries;
        });
    },
    async getCountries() {
      await axios
        .get("https://disease.sh/v3/covid-19/countries?sort=cases")
        .then((response) => {
          this.countries = response.data;
        });
    },
  },
};
</script>
