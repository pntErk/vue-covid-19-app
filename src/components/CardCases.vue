<template lang="">
  <div
    class="p-10 grid grid-cols-1 sm:grid-cols-1 md:grid-cols-2 lg:grid-cols-4 xl:grid-cols-4 gap-5"
  >
    <!--Card 1-->
    <div class="rounded overflow-hidden shadow-lg bg-white">
      <div class="px-6 py-4">
        <div class="font-bold text-xl mb-2">Active</div>
        <p class="text-gray-700 text-base">0</p>
      </div>
    </div>
    <!--Card 2-->
    <div class="rounded overflow-hidden shadow-lg bg-white">
      <div class="px-6 py-4">
        <div class="font-bold text-xl mb-2">Critical</div>
        <p class="text-gray-700 text-base">0</p>
      </div>
    </div>

    <!--Card 3-->
    <div class="rounded overflow-hidden shadow-lg bg-white">
      <div class="px-6 py-4">
        <div class="font-bold text-xl mb-2">Recovered</div>
        <p class="text-gray-700 text-base">1,000,000</p>
      </div>
    </div>

    <!--Card 4-->
    <div class="rounded overflow-hidden shadow-lg bg-white">
      <div class="px-6 py-4">
        <div class="font-bold text-xl mb-2">Deaths</div>
        <p class="text-gray-700 text-base">0</p>
      </div>
    </div>
  </div>
</template>
<script>
import Vue3autocounter from "vue3-autocounter";
export default {
  name: "CardCases",
  components: { "vue3-autocounter": Vue3autocounter },
};
</script>
<style lang=""></style>
