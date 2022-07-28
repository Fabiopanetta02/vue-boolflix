<template>
  <div>
      <ul>
          <li v-for="(film, index) in films" :key="index">
              <SingleCard :info="film"/>
          </li>
      </ul>
  </div>
</template>

<script>
import SingleCard from "../elements/SingleCard.vue";
export default {
    name: "FilmsList",
    components: {
        SingleCard
    },
    props: {
        films: Array
    }
}
</script>

<style lang="scss" scoped>
</style>