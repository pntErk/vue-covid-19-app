<template lang="">
  <div
    class="p-10 grid grid-cols-1 sm:grid-cols-1 md:grid-cols-2 lg:grid-cols-4 xl:grid-cols-4 gap-5 sm:-mx-20 md:mx-1"
  >
    <!--Card 1-->
    <div class="card-one">
      <div class="rounded-xl overflow-hidden shadow-lg bg-white">
        <div class="px-6 py-4">
          <div class="text-xl font-bold mb-1">Active</div>
          <p class="bg-gray-50 rounded-xl text-2xl text-center p-3">
            <vue3-autocounter
              ref="counter"
              :startAmount="0"
              :endAmount="active"
              :duration="1"
              separator=","
            />
          </p>
        </div>
      </div>
    </div>
    <!--Card 2-->
    <div class="rounded-xl overflow-hidden shadow-lg bg-white">
      <div class="px-6 py-4">
        <div class="text-xl font-bold mb-1">Critical</div>
        <p class="bg-gray-50 rounded-xl text-2xl text-center p-3">
          <vue3-autocounter
            ref="counter"
            :startAmount="0"
            :endAmount="critical"
            :duration="1"
            separator=","
          />
        </p>
      </div>
    </div>

    <!--Card 3-->
    <div class="rounded-xl overflow-hidden shadow-lg bg-white">
      <div class="px-6 py-4">
        <div class="text-xl font-bold mb-1">Recovered</div>
        <p class="bg-gray-50 rounded-xl text-2xl text-center p-3">
          <vue3-autocounter
            ref="counter"
            :startAmount="0"
            :endAmount="recovered"
            :duration="1"
            separator=","
          />
        </p>
      </div>
    </div>

    <!--Card 4-->
    <div class="rounded-xl overflow-hidden shadow-lg bg-white">
      <div class="px-6 py-4">
        <div class="text-xl font-bold mb-1">Deaths</div>
        <p class="bg-gray-50 rounded-xl text-2xl text-center p-3">
          <vue3-autocounter
            ref="counter"
            :startAmount="0"
            :endAmount="deaths"
            :duration="1"
            separator=","
          />
        </p>
      </div>
    </div>
  </div>
</template>

<script>
import Vue3autocounter from "vue3-autocounter";
export default {
  name: "CardCases",
  components: { "vue3-autocounter": Vue3autocounter },
  props: ["active", "critical", "deaths", "recovered"],
};
</script>

