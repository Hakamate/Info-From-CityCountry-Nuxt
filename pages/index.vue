<template>
  <div>
    <Nav />

    <div class="p-10">
      <h1 class="text-gray-600">Website All-in-One</h1>
      <div class="grid gap-3 grid-cols-1 lg:grid-cols-2 mt-4">
        <nuxt-link to="/meteo" class="flex lg:mx-auto max-w-2xl sm:flex-row sm:items-stretch items-center flex-col rounded border border-gray-400">
          <img
            class="w-full sm:w-56"
            src="../assets/image/weather.jpg"
            alt="Photo pour météo"
          />
          <div class="px-5 py-3 flex flex-col">
            <h2 class="mb-3 text-gray-800">Weather</h2>
            <p class="text-gray-700">
              A simple application, to get the weather in the whole world and in live. A good way to plan your hollydays or specific events
            </p>
            <div class="mt-auto flex items-center pt-3">
              <img
                class="w-12 h-12 rounded-full mr-4"
                src="../assets/image/thomas.jpg"
                alt="Photo de Thomas"
              />
              <div class="flex flex-col">
              <p class="text-gray-900">
                CLEMENT Thomas
              </p>
              <p class="text-gray-700">
                Age : 20 years
              </p>
              </div>
            </div>
          </div>
        </nuxt-link>
        <nuxt-link to="/country" class="flex lg:mx-auto max-w-2xl sm:flex-row sm:items-stretch items-center flex-col rounded border border-gray-400">
          <img
            class="w-full sm:w-56"
            src="../assets/image/country.jpg"
            alt="Photo pour pays"
          />
          <div class="px-5 py-3 flex flex-col">
            <h2 class="mb-3 text-gray-800">Informations country</h2>
            <p class="text-gray-700">
             An application to retrieve certain information from a targeted country. This can allow you to do a country / capital quiz or find the correct number of citizens.
            </p>
            <div class="mt-auto flex items-center pt-3">
              <img
                class="w-12 h-12 rounded-full mr-4"
                src="../assets/image/thomas.jpg"
                alt="Photo de Thomas"
              />
              <div class="flex flex-col">
              <p class="text-gray-900">
                CLEMENT Thomas
              </p>
              <p class="text-gray-700">
                Age : 20 ans
              </p>
              </div>
            </div>
          </div>
        </nuxt-link>
      </div>
    </div>
  </div>
</template>

<script>
import Nav from "~/components/Nav.vue";

export default {
  components: {
    Nav
  }
};
</script>
