<template>
  <header
    class="myheader bg-white-100 bg-white rounded-lg border border-gray-200 text-black p-4 mb-10 shadow-md sm:px-4"
  >
  <div class="mb:flex mb:justify-between mb:items-center">
    <div class="text-3xl md:text-3xl font-bold mb-3">
      <i class="fa fa-viruses"></i>Covid-19 Dashboard
    </div>
    <p>
      API by
      <a class="text-blue-300 " href="https://disease.sh/docs/">disease.sh</a>
    </p>
  </div>
  </header>
</template>
<script>
export default {
  name: "Topwrapper",
};
</script>
<style>
@media (max-width: 768px) {
 .myheader {
  text-align: center;
 }
}

</style>
