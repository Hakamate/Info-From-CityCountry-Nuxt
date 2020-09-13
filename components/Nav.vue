<template>
  <header class="sticky top-0">
    <nav class="flex items-center justify-between flex-wrap bg-gray-600 text-white p-3">
      <div class="flex items-center flex-no-shrink mr-6">
        <nuxt-link
          to="/">
          <img class="w-8" src="~/assets/image/Logo_NorthConcepts_Alone_White.svg" alt="Logo de l'entreprise Antsane">
        </nuxt-link>
      </div>
      <div :class="open ? 'block': 'hidden'" class="w-full flex-grow sm:flex sm:items-center sm:w-auto">
        <div class="text-sm sm:flex-grow">
          <nuxt-link
            to="/meteo"
            class="no-underline block mt-4 sm:inline-block sm:mt-0 text-teal-lighter hover:text-white mr-4">
            Weather
          </nuxt-link>
          <nuxt-link
            to="/country"
            class="no-underline block mt-4 sm:inline-block sm:mt-0 text-teal-lighter hover:text-white mr-4">
            Information
          </nuxt-link>
        </div>
      </div>
      <div class="block sm:hidden">
        <button @click="toggle"
                class="flex items-center px-3 py-2 border rounded text-teal-lighter border-teal-light hover:text-white hover:border-white">
          <svg class="fill-current h-3 w-3" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg"><title>
            Menu</title>
            <path d="M0 3h20v2H0V3zm0 6h20v2H0V9zm0 6h20v2H0v-2z"/>
          </svg>
        </button>
      </div>
    </nav>
  </header>

</template>

<script>
  export default {
    data() {
      return {
        open: false,
      }
    },
    methods: {
      toggle() {
        this.open = !this.open
      }
    }
  }
</script>
