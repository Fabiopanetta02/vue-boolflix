<template>
  <div>
    <h4>{{info.title || info.name}}</h4>
    <img v-if="!info.poster_path" src="https://ancasadental.com/wp-content/uploads/2020/09/dentalia-placeholder-img-4-750x750.jpg" alt="`${info.original_title || info.original_name}`" class="default-img">
    <img v-else :src="`https://image.tmdb.org/t/p/w342/${info.poster_path}`" alt="`${info.original_title || info.original_name}`">
    <h5>{{info.original_title || info.original_name}}</h5>
    <div class="flags">
      <img v-if="flags.includes(info.original_language)" :src="require(`../../assets/img/${info.original_language}.png`)" :alt="info.original_language">
      <img v-else src="../../assets/img/none.png" alt="Flag not available">
    </div>
    <div>{{info.vote_average}}</div>
  </div>
</template>

<script>

export default {
    name: "SingleCard",
    props: {
        info: Object
    },
    data() {
      return {
        flags: [
          "en",
          "es",
          "fr",
          "it"
        ]
      }
    }
}
</script>

<style lang="scss" scoped>
.default-img{
  width: 342px;
  height: 513px;
}

.flags {
    img {
      width: 50px;
    }
  }
</style>