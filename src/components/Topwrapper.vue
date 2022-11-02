<template>
  <header
    class="myheader bg-white-100 bg-slate-50 text-black p-4 mb-10 shadow-md sm:px-4"
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
  <!-- <div class="header-2">
    <nav class="bg-white py-2 md:py-4">
      <div class="container px-4 mx-auto md:flex md:items-center">
        <div class="flex justify-between items-center">
          <a href="#" class="font-bold text-xl text-indigo-600"
            ><i class="fa fa-viruses"></i>Covid-19 Dashboard</a
          >
        </div>
      </div>
    </nav>
  </div> -->
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
