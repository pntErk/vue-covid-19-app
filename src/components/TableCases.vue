<template>
  <div class="">
    <p >
      Population:
      <vue3-autocounter
        ref="counter"
        :startAmount="0"
        :endAmount="population"
        :duration="1"
        separator=","
      />
    </p>
    <p class="pb-3">
      Affected Countries:
      <vue3-autocounter
        ref="counter"
        :startAmount="0"
        :endAmount="affectedCountries"
        :duration="1"
        separator=","
      />
    </p>
    <div class="overflow-x-auto relative shadow-md rounded-lg py-2 h-96">
      <table class="sm:w-full text-sm text-left text-gray-500">
        <thead class="text-xs text-gray-700 uppercase bg-gray-50">
          <tr>
            <th scope="col" class="py-3 px-6">Country</th>
            <th scope="col" class="py-3 px-6">Total Cases</th>
            <th scope="col" class="py-3 px-6">Recovered</th>
            <th scope="col" class="py-3 px-6">Deaths</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="country in countries" :key="country.iso2">
            <td class="py-3 px-6">
              <div class="flex space-x-5 text">
                <div>
                  <img
                    :src="country.countryInfo.flag"
                    :alt="country.countryInfo.iso2"
                    class="object-contain h-10 w-12"
                  />
                </div>

                <p class="mt-2">
                  {{ country.country }}
                </p>
              </div>
            </td>

            <td class="py-3 px-6">
              <vue3-autocounter
                ref="counter"
                :startAmount="0"
                :endAmount="country.cases"
                :duration="1"
                separator=","
              />
            </td>
            <td class="py-3 px-6">
              <vue3-autocounter
                ref="counter"
                :startAmount="0"
                :endAmount="country.recovered"
                :duration="1"
                separator=","
              />
            </td>
            <td class="py-3 px-6">
              <vue3-autocounter
                ref="counter"
                :startAmount="0"
                :endAmount="country.deaths"
                :duration="1"
                separator=","
              />
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
  name: "TableCases",
  components: { "vue3-autocounter": Vue3autocounter },
  props: ["population", "affectedCountries", "countries"],
};
</script>
<style></style>
