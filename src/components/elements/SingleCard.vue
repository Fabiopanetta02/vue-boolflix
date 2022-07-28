<template>
  <div>
    <h4>{{info.title}}</h4>
    <h5>{{info.original_title}}</h5>
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
</style>