<template>
  <div>
    <p>
      Population:
      <vue3-autocounter
        ref="counter"
        :startAmount="0"
        :endAmount="population"
        :duration="1"
        separator=","
      />
    </p>
    <p>
      Affected Countries:
      <vue3-autocounter
        ref="counter"
        :startAmount="0"
        :endAmount="affectedCountries"
        :duration="1"
        separator=","
      />
    </p>
    <div class="overflow-x-auto relative shadow-md sm:rounded-lg bg-white">
      <table class="w-full text-sm text-left text-gray-500">
        <thead class="text-xs text-gray-700 uppercase bg-gray-50">
          <tr>
            <th scope="col" class="py-3 px-6">Country</th>
            <th scope="col" class="py-3 px-6">Total Cases</th>
            <th scope="col" class="py-3 px-6">Recovered</th>
            <th scope="col" class="py-3 px-6">Deaths</th>
          </tr>
        </thead>
        <tbody>
          <tr class="bg-white border-b">
            <th
              scope="row"
              class="py-4 px-6 font-medium text-gray-900 whitespace-nowrap"
            >
              Apple MacBook Pro 17"
            </th>
            <td class="py-4 px-6">Sliver</td>
            <td class="py-4 px-6">Laptop</td>
            <td class="py-4 px-6">$2999</td>
          </tr>
          <tr class="bg-gray-50 border-b">
            <th
              scope="row"
              class="py-4 px-6 font-medium text-gray-900 whitespace-nowrap"
            >
              Microsoft Surface Pro
            </th>
            <td class="py-4 px-6">White</td>
            <td class="py-4 px-6">Laptop PC</td>
            <td class="py-4 px-6">$1999</td>
          </tr>
          <tr class="bg-white border-b">
            <th
              scope="row"
              class="py-4 px-6 font-medium text-gray-900 whitespace-nowrap"
            >
              Magic Mouse 2
            </th>
            <td class="py-4 px-6">Black</td>
            <td class="py-4 px-6">Accessories</td>
            <td class="py-4 px-6">$99</td>
          </tr>
          <tr class="bg-gray-50 border-b">
            <th
              scope="row"
              class="py-4 px-6 font-medium text-gray-900 whitespace-nowrap"
            >
              Google Pixel Phone
            </th>
            <td class="py-4 px-6">Gray</td>
            <td class="py-4 px-6">Phone</td>
            <td class="py-4 px-6">$799</td>
          </tr>
          <tr class="bg-white border-b">
            <th
              scope="row"
              class="py-4 px-6 font-medium text-gray-900 whitespace-nowrap"
            >
              Apple Watch 5
            </th>
            <td class="py-4 px-6">Red</td>
            <td class="py-4 px-6">Wearables</td>
            <td class="py-4 px-6">$999</td>
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
  props: ["population", "affectedCountries"],
};
</script>
<style></style>
