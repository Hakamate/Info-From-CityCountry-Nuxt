<template>
  <div>
    <Nav/>
    <div class="">
      <form action="" @submit.prevent="getCityWeather" method="post" class="flex items-stretch" netlify>
        <input class="p-5 w-full text-2xl"
               id="city"
               v-model="city"
               type="city"
               name="city"
               placeholder="Select a City"
        >
      </form>
      <div class="grid sm:gap-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 xl:grid-cols-5">
        <div class="flex items-center justify-between cardMeteo font-bold"
           :class="(block.temp < 15) ? 'bg-blue-900' : 'bg-red-900'" v-for="(block,index) in globalData" v-bind:key="index">
          <img class="whather-icon m-5"
              v-bind:src="'https://www.weatherbit.io/static/img/icons/' + block.weather.icon +'.png'" alt="Icon météo">
          <div class="py-5 text-white">
            {{block.timestamp_local.substring(11, 16)}}
          </div>
          <div class="p-5 pl-0 text-white text-right deg">
            {{block.temp}}°C
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
  import Nav from '~/components/Nav.vue'
  import axios from "axios";
  import '~/assets/css/meteo.css';

  export default {
    components: {
      Nav
    },
    data() {
      return {
        city: '',
        count: 48,
        globalData: []
      }
    },
    methods:{
      getCityWeather: function () {
        axios.get(`https://api.weatherbit.io/v2.0/forecast/hourly?city=${this.city}&key=e0e13d8fd25d4930afedc4c6766eda26&hours=${this.count}`)
          .then(response => {
            this.globalData = response.data.data;
          })
      }
    }
  }
</script>

