<template>
  <!-- <header
    class="myheader bg-white-100 bg-white border border-gray-200 text-black p-4 mb-10 shadow-md sm:px-4"
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
  </header> -->
  <nav
    class="px-2 bg-white border-gray-200 dark:bg-gray-900 dark:border-gray-700"
  >
    <div class="container flex flex-wrap justify-between items-center mx-auto">
      <a href="#" class="flex items-center">
        <i class="fa fa-viruses text-white" />
        <span
          class="self-center text-xl font-semibold whitespace-nowrap dark:text-white"
          >Covid-19 Dashboard</span
        >
      </a>
      <button
        data-collapse-toggle="mobile-menu"
        type="button"
        class="inline-flex justify-center items-center ml-3 text-gray-400 rounded-lg md:hidden hover:text-gray-900 focus:outline-none focus:ring-2 focus:ring-blue-300 dark:text-gray-400 dark:hover:text-white dark:focus:ring-gray-500"
        aria-controls="mobile-menu-2"
        aria-expanded="false"
      >
        <span class="sr-only">Open main menu</span>
        <svg
          class="w-6 h-6"
          aria-hidden="true"
          fill="currentColor"
          viewBox="0 0 20 20"
          xmlns="http://www.w3.org/2000/svg"
        >
          <path
            fill-rule="evenodd"
            d="M3 5a1 1 0 011-1h12a1 1 0 110 2H4a1 1 0 01-1-1zM3 10a1 1 0 011-1h12a1 1 0 110 2H4a1 1 0 01-1-1zM3 15a1 1 0 011-1h12a1 1 0 110 2H4a1 1 0 01-1-1z"
            clip-rule="evenodd"
          ></path>
        </svg>
      </button>

      <div class="hidden w-full md:block md:w-auto" id="mobile-menu">
        <ul
          class="flex flex-col p-4 mt-4 bg-gray-50 rounded-lg border border-gray-100 md:flex-row md:space-x-8 md:mt-0 md:text-sm md:font-medium md:border-0 md:bg-white dark:bg-gray-800 md:dark:bg-gray-900 dark:border-gray-700"
        >
          <li>
            <a
              href="#"
              class="block py-2 pr-4 pl-3 text-white bg-blue-700 rounded md:bg-transparent md:text-blue-700 md:p-0 md:dark:text-white dark:bg-blue-600 md:dark:bg-transparent"
              aria-current="page"
              >Home</a
            >
          </li>
          
          <li>
            <a
              href="#"
              class="block py-2 pr-4 pl-3 text-gray-700 rounded hover:bg-gray-100 md:hover:bg-transparent md:border-0 md:hover:text-blue-700 md:p-0 dark:text-gray-400 md:dark:hover:text-white dark:hover:bg-gray-700 dark:hover:text-white md:dark:hover:bg-transparent"
              >About</a
            >
          </li>
        </ul>
      </div>
    </div>
  </nav>
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
