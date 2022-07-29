<template>
<section id="series">
    <div class="container">
      <h2>Serie TV</h2>
      <ul class="list-style-type-none">
          <li v-for="(serie, index) in series" :key="index" class="item">
              <SingleCard :info="serie"/>
          </li>
      </ul>
    </div>
</section>
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
@import '../../assets/scss/vars';
#series{
    margin: 20px 0px;

    h2{
    color: #fff;
    padding: 20px;
    }
    .item {
    width: calc(100% / 4);
    color: $text-white;
    padding: 10px 20px;
    }
}
</style>