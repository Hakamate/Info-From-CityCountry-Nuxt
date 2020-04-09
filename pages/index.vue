<template>
  <div>
    <Nav />

    <div class="p-10">
      <h1 class="text-gray-600">Le site tout-en-un</h1>
      <div class="grid gap-3 grid-cols-1 lg:grid-cols-2 mt-4">
        <nuxt-link to="/meteo" class="flex lg:mx-auto max-w-2xl sm:flex-row sm:items-stretch items-center flex-col rounded border border-gray-400">
          <img
            class="w-full sm:w-56"
            src="../assets/image/weather.jpg"
            alt="Photo pour météo"
          />
          <div class="px-5 py-3 flex flex-col">
            <h2 class="mb-3 text-gray-800">La météo de demain</h2>
            <p class="text-gray-700">
              Une application simple, permettant d'obtenir la météo dans le monde
              entier et en direct. Un bon moyen de prévoir ses sorties au ski, à
              la mer ou même ses vacances.
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
        <nuxt-link to="/meteo" class="flex lg:mx-auto max-w-2xl sm:flex-row sm:items-stretch items-center flex-col rounded border border-gray-400">
          <img
            class="w-full sm:w-56"
            src="../assets/image/weather.jpg"
            alt="Photo pour météo"
          />
          <div class="px-5 py-3 flex flex-col">
            <h2 class="mb-3 text-gray-800">La météo de demain</h2>
            <p class="text-gray-700">
              Une application simple, permettant d'obtenir la météo dans le monde
              entier et en direct. Un bon moyen de prévoir ses sorties au ski, à
              la mer ou même ses vacances.
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
