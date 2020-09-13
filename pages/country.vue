<template>
  <div>
    <Nav />
    <div class>
      <form
        action
        @submit.prevent="getCityWeather"
        method="post"
        class="flex items-stretch"
        netlify
      >
        <input
          class="p-5 w-full text-2xl"
          id="country"
          v-model="country"
          type="country"
          name="country"
          placeholder="Select a Country"
        />
      </form>

      <div class="m-10 flex items-start flex-col font-bold">
        <div class="text-gray-900 text-xl" :class="this.globalData.capital ? 'block' : 'hidden'">
          Capital :
          <span class="text-gray-700 font-light">{{this.globalData.capital}}</span>
        </div>
        <div class="text-gray-900 text-xl" :class="this.globalData.region ? 'block' : 'hidden'">
          Region :
          <span class="text-gray-700 font-light">{{this.globalData.region}}</span>
        </div>
        <div class="text-gray-900 text-xl" :class="this.globalData.population ? 'block' : 'hidden'">
          Population :
          <span
            class="text-gray-700 font-light"
          >{{Intl.NumberFormat().format(this.globalData.population)}}</span>
        </div>
        <div
          class="text-gray-900 text-xl"
          :class="this.globalData.callingCodes ? 'block' : 'hidden'"
        >
          Call number :
          <span class="text-gray-700 font-light">{{this.globalData.callingCodes}}</span>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Nav from "~/components/Nav.vue";
import axios from "axios";

export default {
  components: {
    Nav,
  },
  data() {
    return {
      country: "",
      globalData: [],
    };
  },
  mounted: function () {
    axios
      .get(`https://restcountries.eu/rest/v2/name/France`)
      .then((response) => {
        console.log(response.data[0]);
      });
  },
  methods: {
    getCityWeather: function () {
      axios
        .get(`https://restcountries.eu/rest/v2/name/${this.country}`)
        .then((response) => {
          this.globalData = response.data[0];
          console.log(this.globalData);
        });
    },
  },
};
</script>

