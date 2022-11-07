<template>
  <div>
    <div class="grid grid-cols-2">
      <p class="py-2 font-sans font-bold sm:text-base md:lg:text-xl">
        Timeline Table
      </p>
    </div>
    <div class="overflow-auto flex-grow flex-col rounded-lg h-96">
      <table class="relative w-full text-sm text-left text-gray-500">
        <thead class="text-xs text-gray-700 uppercase">
          <tr>
            <th scope="col" class="sticky top-0 py-3 px-6 bg-gray-50">
              Timeline
            </th>
            <th scope="col" class="sticky top-0 py-3 px-6 bg-gray-50">
              Total Cases
            </th>
            <th scope="col" class="sticky top-0 py-3 px-6 bg-gray-50">
              Deaths
            </th>
            <th scope="col" class="sticky top-0 py-3 px-6 bg-gray-50">
              Recovered
            </th>
          </tr>
        </thead>
        <tbody clas="divide-y">
          <tr class="border-b" >
            <td class="py-3 px-6">
               อะไร
            </td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</template>
<script>
import Vue3autocounter from "vue3-autocounter";

export default {
  name: "TimelineTable",
  components: { "vue3-autocounter": Vue3autocounter },
  props: ["historicalData"],
  data() {
    return {
      casesdate: [],
      casestotal: [],
      deathstotal: [],
      recoveredtotal: [],
      alldata:[],
      limit: 30,
    };
  },
  watch: {
    historicalData(val) {
      this.casesdate = Object.getOwnPropertyNames(val.cases);
      this.casestotal = Object.values(val.cases);
      this.deathstotal = Object.values(val.deaths);
      this.recoveredtotal = Object.values(val.recovered);
      console.log(this.alldata)
    },
  },

};
</script>

<!-- https://stackoverflow.com/questions/55002301/merge-object-with-vuejs-and-axios -->
<!-- https://stackoverflow.com/questions/54627659/how-merge-mutil-object-in-array-with-lodash -->