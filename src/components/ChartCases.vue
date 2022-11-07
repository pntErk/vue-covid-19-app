<template>
  <div class="container">
    <p class="py-2 font-sans font-bold sm:text-base md:lg:text-xl">
      Records in 30 Days
    </p>
    <div class="grid grid-cols-2 gap-2">
      <p class="mb-3 sm:text-sm md:lg:text-base sm:-mt-3">
        (Covid-19 data sourced from Johns Hopkins University, updated every 10
        minutes)
      </p>
    </div>
    <apexchart
      ref="chart"
      type="area"
      width="100%"
      height="350"
      :options="options"
      :series="series"
    ></apexchart>
  </div>
</template>

<script>
import VueApexCharts from "vue3-apexcharts";
export default {
  name: "ChartCases",
  components: { apexchart: VueApexCharts },
  props: ["chartData"],
  data() {
    return {
      options: {
        chart: {
          id: "daily-cases",
        },
        xaxis: {},
      },
      series: [],
    };
  },
  watch: {
    chartData(val) {
      const casesdate = Object.getOwnPropertyNames(val.cases);
      const casestotal = Object.values(val.cases);
      const deathstotal = Object.values(val.deaths);
      const recoveredtotal = Object.values(val.recovered);
      this.$refs.chart.updateOptions({
        chart: {
          type: "area",
          stacked: false,
          height: 350,
          zoom: {
            type: "x",
            enabled: true,
            autoScaleYaxis: true,
          },
        },
        xaxis: {
          type: "datetime",
          categories: casesdate,
        },
        toolbar: {
          autoSelected: "zoom",
        },
        markers: {
          size: 0,
        },
        dataLabels: {
          enabled: false,
        },
        colors: ["#00a4db", "#ff2323", "#229977"],
        legend: {
          fontSize: "14px",
          fontFamily: "Space Mono",
          labels: {
            colors: "#A8B2CD",
          },
        },
        stroke: {
          curve: "smooth",
        },
        fill: {
          type: "gradient",
          gradient: {
            shadeIntensity: 1,
            inverseColors: false,
            opacityFrom: 0.5,
            opacityTo: 0,
            stops: [0, 90, 100],
          },
        },
      });
      const series = [
        {
          name: "Confirmed",
          data: casestotal,
        },
        {
          name: "Deaths",
          data: deathstotal,
        },
        {
          name: "Recovered",
          data: recoveredtotal,
        },
      ];
      this.$refs.chart.updateSeries(series);
    },
  },
};
</script>
