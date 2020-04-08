<template>
  <div>
    <Nav/>
    <div class="">
      <form action="" @submit.prevent="getCityWather" method="post" class="flex items-stretch" netlify>
        <input class="p-5 w-full text-2xl"
               id="city"
               v-model="city"
               type="city"
               name="city"
               placeholder="Veuillez choisir une ville"
        >
      </form>
      <div class="bg-gray-200 flex items-center justify-between cardMeteo bg-gray-700 font-bold"
           :class="(block.temp < 15) ? 'bg-blue-900' : 'bg-red-900'" v-for="block in globalData">
        <img class="whather-icon m-5"
             v-bind:src="'https://www.weatherbit.io/static/img/icons/' + block.weather.icon +'.png'" alt="">
        <div class="p-5 text-white">
          {{block.timestamp_local.substring(11, 16)}}
        </div>
        <div class="p-5 text-white text-right deg">
          {{block.temp}}°C
        </div>
      </div>
    </div>
  </div>
</template>

<script>
  import Nav from '~/components/Nav.vue'
  import axios from "axios";

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
      getCityWather: function () {
        axios.get(`https://api.weatherbit.io/v2.0/forecast/hourly?city=${this.city}&key=6b32c9bff95f4ba1bd599139b3f50c8c&hours=${this.count}`)
          .then(response => {
            this.globalData = response.data.data;
          })
      }
    }
  }
</script>

