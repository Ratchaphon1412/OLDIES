<script setup>
import { onMounted } from 'vue'
import {
  initAccordions,
  initCarousels,
  initCollapses,
  initDials,
  initDismisses,
  initDrawers,
  initDropdowns,
  initModals,
  initPopovers,
  initTabs,
  initTooltips,
} from 'flowbite'

// initialize components based on data attribute selectors
onMounted(() => {
  initAccordions()
  initCarousels()
  initCollapses()
  initDials()
  initDismisses()
  initDrawers()
  initDropdowns()
  initModals()
  initPopovers()
  initTabs()
  initTooltips()
})
</script>

<template>
  <nav
    class="fixed w-full z-20 top-0 left-0 transition-colors duration-300"
    :class="[scrolled ? 'background-solid-nav' : 'bg-transparent']"
  >
    <div
      class="max-w-screen-xl flex flex-wrap items-center justify-between mx-auto p-4"
    >
      <a href="https://flowbite.com/" class="flex items-center">
        <img src="OldiesLogo.ico" class="h-8 mr-3" alt="Flowbite Logo" />
        <span
          class="self-center text-2xl font-semibold whitespace-nowrap text-white"
          >OLDIES</span
        >
      </a>
      <button
        data-collapse-toggle="navbar-default"
        type="button"
        class="inline-flex items-center p-2 ml-3 text-sm text-white rounded-lg md:hidden focus:outline-none focus:ring-2"
        aria-controls="navbar-default"
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

      <div class="hidden w-full md:block md:w-auto" id="navbar-default">
        <ul
          class="font-medium flex flex-col items-center p-4 md:p-0 mt-4 border border-gray-100 rounded-lg md:flex-row md:space-x-8 md:mt-0 md:border-0"
        >
          <li>
            <a
              v-scroll-to="'#home'"
              class="block py-2 pl-3 pr-4 text-white rounded md:bg-transparent md:text-white md:p-0 dark:text-white md:hover:text-blue-700"
              aria-current="page"
              >Home</a
            >
          </li>
          <li>
            <a
              v-scroll-to="'#problem'"
              class="block py-2 pl-3 pr-4 text-white rounded md:hover:bg-transparent md:border-0 md:hover:text-blue-700 md:p-0"
              >Problem</a
            >
          </li>
          <li>
            <a
              v-scroll-to="'#solution'"
              class="block py-2 pl-3 pr-4 text-white rounded md:hover:bg-transparent md:border-0 md:hover:text-blue-700 md:p-0"
              >Solution</a
            >
          </li>
          <!-- <li>
            <a
              v-scroll-to="'#target'"
              class="block py-2 pl-3 pr-4 text-white rounded hover:bg-gray-100 md:hover:bg-transparent md:border-0 md:hover:text-blue-700 md:p-0"
              >Target</a
            >
          </li> -->
          <li class="">
            <button
              v-scroll-to="'#contact'"
              type="button"
              class="text-white bg-[#2D3648] focus:ring-4 focus:outline-none font-medium rounded-lg text-sm px-4 py-2 text-center mr-3 md:mr-0"
            >
              Contact
            </button>
          </li>
        </ul>
      </div>
    </div>
  </nav>
</template>
<script>
import { VScrollTo } from 'vue-scrollto'

export default {
  components: {
    VScrollTo,
  },
  data() {
    return {
      scrolled: false,
    }
  },
  mounted() {
    window.addEventListener('scroll', this.handleScroll)
  },
  beforeDestroy() {
    window.removeEventListener('scroll', this.handleScroll)
  },
  methods: {
    handleScroll() {
      this.scrolled = window.scrollY > 0
    },
  },
}
</script>

<style scoped>
.background-solid-nav {
  background-color: rgba(0, 0, 0, 0.6);
}
</style>
