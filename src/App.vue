<template>
  <div>
    <header>
      <TheHeader @search="searching"/>
    </header>
    <main>
      <BaseMain :films="films" :series="series"/>
    </main>
    <TheFooter />
  </div>
</template>

<script>
import TheHeader from './components/macro/TheHeader.vue'
import BaseMain from './components/macro/BaseMain.vue'
import TheFooter from './components/macro/TheFooter.vue'

import axios from 'axios';

export default {
  name: 'App',
  components: {
    TheHeader,
    BaseMain,
    TheFooter,
  },
  data(){
    return{
      films: [],
      series: []
    }
  },
  methods: {
    searching(payload){
      // call server for movies search
      axios.get("https://api.themoviedb.org/3/search/movie", {
        params: {
          api_key: "869adbdd8dc3114da19f19c812dbedb9",
          query: payload,
          language: "it-IT"
        }
      })
      .then((response) => {
        console.log(response.data.results);
        this.films = response.data.results;
      })
      .catch((error) => {
        console.log(error);
      });

      // call server for tv series search
      axios.get("https://api.themoviedb.org/3/search/tv", {
        params: {
          api_key: "869adbdd8dc3114da19f19c812dbedb9",
          query: payload,
          language: "it-IT"
        }
      })
      .then((response) => {
        console.log(response.data.results);
        this.series = response.data.results;
      })
      .catch((error) => {
        console.log(error);
      });
    }
  }
}
</script>

<style lang="scss">
  @import './assets/scss/style.scss';
</style>
