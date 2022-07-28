<template>
  <div>
    <h4>{{info.title}}</h4>
    <h5>{{info.original_title}}</h5>
    <p>{{info.original_language}}</p>
    <p>{{info.vote_average}}</p>
  </div>
</template>

<script>
export default {
    name: "SingleCard",
    props: {
        info: Object
    }
}
</script>

<style lang="scss" scoped>
</style>