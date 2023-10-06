<template>
  <div id="app">
    <WeatherTable :klokkeslett="info.data.timeUTC" :temperature="info.data.temp" />
    <WindArrow :beaufort="info.data.beaufort" :test="info.data" />
  </div>
</template>

<script>
// import { D3BarChart } from 'vue-d3-charts';
import axios from 'axios';
import WeatherTable from './components/WeatherTable.vue'
import WindArrow from './components/WindArrow.vue';

export default {
  components: {
    // D3BarChart,
    WeatherTable,
    WindArrow
  },
  data() {
    return {
      timer: null,
      info: null,
      chart_title: 'Your title goes here',
      chart_source: 'Your source goes here',
      chart_data: [
        //...
        { hours: 1648, production: 9613, year: '2007' },
        { hours: 2479, production: 6315, year: '2008' },
        { hours: 3200, production: 2541, year: '2009' }
      ],
      chart_config: {
        key: 'year',
        currentKey: '2004',
        values: ['hours'],
        axis: {
          yTicks: 3
        },
        color: {
          default: '#222f3e',
          current: '#41B882'
        }
      }
    }
  },
  methods: {
    get_data: function () {
      axios
        .get('https://skodje.org/verdata/flem/customclientraw.txt')
        .then(response => (this.info = response))
    },
    cancelAutoUpdate() {
      clearInterval(this.timer);
    },
  },
  mounted() {
    this.timer = setInterval(() => {
      this.get_data()
    }, 1000)
  },
  beforeDestroy() {
    this.cancelAutoUpdate();
  },

}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
