<script setup>

</script>

<template>
  <div class="home">Hello World</div>
</template>

<script>
export default {
  name: "HomeView",
  components: {},
  data(){
    return {
      loading: true,
      title: 'cases',
      
    }
  },
  methods: {
    async fetchCovidData() {
      const res = await fetch("https://disease.sh/v3/covid-19/all");
      const data = await res.json();
      return data;
    },
  },
  async created() {
    const data = this.fetchCovidData()
    console.log(data)
  },
};
</script>
