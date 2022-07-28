<template>
  <div>
    <FilmsList :films="films"/>
    <SeriesList :series="series"/>
  </div>
</template>

<script>
import FilmsList from '../sections/FilmsList.vue';
import SeriesList from '../sections/SeriesList.vue';

export default {
    name: 'BaseMain',
    components: {
      FilmsList,
      SeriesList
    },
    props: {
      films: Array,
      series: Array
    }
}
</script>

<style lang="scss" scoped>
</style>