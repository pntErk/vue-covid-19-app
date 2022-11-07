<template>
  <button
    @click="open = true"
    type="button"
    class="text-white hover:bg-blue-700 hover:text-blue-g focus:ring-4 focus:outline-none focus:ring-blue-300 font-medium rounded-full text-sm text-center inline-flex items-center"
  >
    <svg
      xmlns="http://www.w3.org/2000/svg"
      fill="none"
      viewBox="0 0 24 24"
      stroke-width="1.5"
      stroke="currentColor"
      class="w-6 h-6"
    >
      <path
        stroke-linecap="round"
        stroke-linejoin="round"
        d="M11.25 11.25l.041-.02a.75.75 0 011.063.852l-.708 2.836a.75.75 0 001.063.853l.041-.021M21 12a9 9 0 11-18 0 9 9 0 0118 0zm-9-3.75h.008v.008H12V8.25z"
      />
    </svg>
  </button>
  <Teleport to="body">
    <!-- Modal information -->
    <div v-if="open" OnClickOutside @click="open = false" class="modal">
      <div
        class="modal-backdrop fixed bg-black w-full h-full bg-opacity-20 inset-0 outline-none overflow-x-hidden overflow-y-auto"
      >
        <div class="flex justify-center pt-24">
          <div
            class="modal bg-white shadow-xl p-4 rounded-lg w-auto"
            role="dialog"
            ref="modal"
          >
            <div
              class="modal-content border-none relative flex flex-col w-full pointer-events-auto bg-white bg-clip-padding rounded-md outline-none text-current"
            >
              <div
                class="modal-header flex flex-shrink-0 items-center justify-between p-4 border-b border-gray-200 rounded-t-md"
              >
                <h5 class="text-xl font-medium leading-normal text-gray-800">
                  About
                </h5>
                <button
                  @click="open = false"
                  type="button"
                  class="btn-close box-content w-4 h-4 p-1 text-black border-none rounded-none opacity-50 focus:shadow-none focus:outline-none focus:opacity-100 hover:text-black hover:opacity-75 hover:no-underline"
                >
                  <svg
                    xmlns="http://www.w3.org/2000/svg"
                    fill="none"
                    viewBox="0 0 24 24"
                    strokeWidth="{1.5}"
                    stroke="currentColor"
                    className="w-6 h-6"
                  >
                    <path
                      strokeLinecap="round"
                      strokeLinejoin="round"
                      d="M6 18L18 6M6 6l12 12"
                    />
                  </svg>
                </button>
              </div>
              <div class="modal-body relative p-4">
                <p class="mb-3">
                  API Used:
                  <a class="no-underline hover:underline" :href="diseaseapi" target="_blank">disease.sh</a>
                </p>
                <p class="mb-3">
                  Data Source:
                  <a class="no-underline hover:underline" :href="jhu" target="_blank">Johns Hopkins University</a>,
                  and
                  <a class="no-underline hover:underline" :href="worldometer" target="_blank">Worldometers</a>
                </p>
                <p class="mb-3">
                  Built with <a class="no-underline hover:underline" :href="vuejs" target="_blank">Vite + Vue 3</a>,
                  <a class="no-underline hover:underline" :href="tailwind" target="_blank">Tailwind CSS</a>,
                  <a class="no-underline hover:underline" :href="chart" target="_blank">Chart</a>, and
                  <a class="no-underline hover:underline" :href="countup" target="_blank">Count Up</a>
                </p>
                <p class="text-center font-bold pt-5">Made by Phongpanot Phumphua</p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </Teleport>
</template>

<script>

export default {
  name: "AboutPopup",
  data() {
    return {
      open: false,
      vuejs: "https://vitejs.dev/guide/",
      tailwind: "https://tailwindcss.com/",
      diseaseapi: "https://disease.sh/docs/",
      jhu: "https://github.com/CSSEGISandData/COVID-19",
      worldometer: "https://www.worldometers.info/coronavirus/",
      chart: "https://github.com/apertureless/vue-chartjs",
      countup: "https://github.com/ps-cristopher/vue3-autocounter",
      github: "https://github.com/Erk-dev/vue-covid-19-app",
    };
  },

};
</script>