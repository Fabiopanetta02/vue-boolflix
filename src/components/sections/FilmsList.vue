<template>
  <div class="container">
    <h2>Film</h2>
      <ul class="d-flex">
          <li v-for="(film, index) in films" :key="index" class="item">
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
@import '../../assets/scss/vars';
h2{
    color: #fff;
    padding: 20px;
}
.item {
    width: calc(100% / 4);
    color: $text-white;
    padding: 10px 20px;
}
</style>