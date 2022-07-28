<template>
  <div>
    <h4>{{info.title || info.name}}</h4>
    <img v-if="!info.poster_path" src="https://ancasadental.com/wp-content/uploads/2020/09/dentalia-placeholder-img-4-750x750.jpg" alt="`${info.original_name}`" class="default-img">
    <img v-else :src="`https://image.tmdb.org/t/p/w342/${info.poster_path}`" alt="`${info.original_name}`">
    <h5>{{info.original_title || info.original_name}}</h5>
    <lang-flag :iso="`${info.original_language}`"/>
    <p>{{info.vote_average}}</p>
  </div>
</template>

<script>
import LangFlag from 'vue-lang-code-flags';

export default {
    name: "SingleCard",
    components: {
      LangFlag
    },
    props: {
        info: Object
    }
}
</script>

<style lang="scss" scoped>
.default-img{
  width: 342px;
  height: 513px;
}
</style>