<template>
  <nav
    class="px-2 bg-gray-900 border-gray-700"
  >
    <div class="container flex flex-wrap justify-between items-center mx-auto">
      <a href="/" class="flex items-center">
        <i class="fa fa-viruses text-white" />
        <span
          class="self-center text-xl font-semibold whitespace-nowrap text-white"
          >Covid-19 Dashboard</span
        >
      </a>
      <button
        data-collapse-toggle="mobile-menu"
        type="button"
        class="inline-flex justify-center items-center ml-3 rounded-lg md:hidden focus:outline-none focus:ring-2 focus:ring-blue-300 text-gray-400 hover:text-white focus:ring-gray-500"
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
          class="flex flex-col p-4 mt-4 mx-5 rounded-lg border md:flex-row md:space-x-8 md:mt-0 md:text-sm md:font-medium md:border-0 bg-gray-800 md:bg-gray-900 border-gray-700"
        >
          <li>
            <a
              href="/"
              class="block py-2 pr-4 pl-3 text-white bg-blue-700 rounded md:text-blue-700 md:p-0 md:text-white bg-blue-600 md:bg-transparent"
              aria-current="page"
              >Home</a
            >
          </li>

          <li>
            <AboutPopup />
          </li>
        </ul>
      </div>
    </div>
  </nav>
</template>

<script>
import AboutPopup from "./AboutPopup.vue";
export default {
  name: "Topwrapper",
  components: {
    AboutPopup,
  },
};
</script>
<style>
@media (max-width: 768px) {
  .myheader {
    text-align: center;
  }
}
</style>
