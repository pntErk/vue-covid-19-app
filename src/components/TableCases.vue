<template>
  <div>
    <div class="grid grid-cols-2">
      <p class="py-2 font-sans font-bold sm:text-base md:lg:text-xl">
        Affected Countries
      </p>
    </div>
    <p class="w-1/2 sm:text-sm md:text-base">
      Population:
      <vue3-autocounter
        ref="counter"
        :startAmount="0"
        :endAmount="population"
        :duration="1"
        separator=","
      />
    </p>
    <p class="pb-3 w-1/2 sm:text-sm md:text-base">
      Affected Countries:
      <vue3-autocounter
        ref="counter"
        :startAmount="0"
        :endAmount="affectedCountries"
        :duration="1"
        separator=","
      />
    </p>
    <div class="overflow-auto flex-grow flex-col rounded-lg h-96">
      <table class="relative w-full text-sm text-left text-gray-500">
        <thead class="text-xs text-gray-700 uppercase">
          <tr>
            <th scope="col" class="sticky top-0 py-3 px-6 bg-gray-50">
              Country
            </th>
            <th scope="col" class="sticky top-0 py-3 px-6 bg-gray-50">
              Total Cases
            </th>
            <th scope="col" class="sticky top-0 py-3 px-6 bg-gray-50">
              Recovered
            </th>
            <th scope="col" class="sticky top-0 py-3 px-6 bg-gray-50">
              Deaths
            </th>
          </tr>
        </thead>
        <tbody clas="divide-y">
          <tr v-for="country in countries" :key="country.iso2" class="border-b">
            <td class="py-3 px-6">
              <div class="flex space-x-5 text">
                <div>
                  <img
                    :src="country.countryInfo.flag"
                    :alt="country.countryInfo.iso2"
                    class="sm:object-scale-down md:object-contain sm:h-6 sm:w-10 md:h-10 md:w-12"
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
