<template>
  <div>
    <FilmsList :films="films"/>
  </div>
</template>

<script>
import FilmsList from '../sections/FilmsList.vue';

export default {
    name: 'BaseMain',
    components: {
      FilmsList
    },
    props: {
      films: Array
    }
}
</script>

<style lang="scss" scoped>
</style>