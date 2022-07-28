<template>
  <div>
      <h2>Series List</h2>
      <ul>
          <li v-for="(serie, index) in series" :key="index">
              <SingleCard :info="serie"/>
          </li>
      </ul>
  </div>
</template>

<script>
import SingleCard from "../elements/SingleCard.vue";
export default {
    name: "SeriesList",
    components: {
        SingleCard
    },
    props: {
        series: Array
    }
}
</script>

<style lang="scss" scoped>
</style>