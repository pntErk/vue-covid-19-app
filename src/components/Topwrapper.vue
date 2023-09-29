<template>
  <div class="bg-gray-900 border-gray-700">
    <nav
      class="container px-6 py-3 mx-auto md:flex md:justify-between md:items-center flex-wrap justify-between"
    >
      <div class="flex items-center justify-between">
        <router-link
          to="/"
          class="text-xl font-bold text-gray-800 md:text-2xl hover:text-blue-400"
          ><i class="fa fa-viruses text-white" />
          <span
            class="self-center text-xl font-semibold whitespace-nowrap text-white"
            >Covid-19 Dashboard</span
          >
        </router-link>
        <!-- Mobile menu button -->
        <div @click="showMenu = !showMenu" class="flex md:hidden">
          <button
            type="button"
            class="text-white hover:text-gray-400 focus:outline-none focus:text-gray-400"
          >
            <svg viewBox="0 0 24 24" class="w-6 h-6 fill-current">
              <path
                fill-rule="evenodd"
                d="M4 5h16a1 1 0 0 1 0 2H4a1 1 0 1 1 0-2zm0 6h16a1 1 0 0 1 0 2H4a1 1 0 0 1 0-2zm0 6h16a1 1 0 0 1 0 2H4a1 1 0 0 1 0-2z"
              ></path>
            </svg>
          </button>
        </div>
      </div>
      <!--  -->
      <ul
        :class="showMenu ? 'flex' : 'hidden'"
        class="flex-col px-7 py-2 p-3 mt-4 md:flex md:space-y-0 md:flex-row md:items-center md:space-x-10 md:mt-0"
      >
        <li>
          <a
            href="/"
            class="text-white bg-blue-700 rounded md:bg-transparent md:text-blue-700 md:p-0 md:dark:text-white dark:bg-blue-600 md:dark:bg-transparent"
            aria-current="page"
            >Home</a
          >
        </li>
        <li class="pt-2">
          <AboutPopup />
        </li>
      </ul>
    </nav>
  </div>
</template>

<script>
import AboutPopup from "./AboutPopup.vue";
export default {
  name: "Topwrapper",
  components: {
    AboutPopup,
  },
  data() {
    return {
      showMenu: false,
    };
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
