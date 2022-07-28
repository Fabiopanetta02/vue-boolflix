<template>
  <div>
    <TheHeader />
    <BaseMain />
    <TheFooter />
  </div>
</template>

<script>
import TheHeader from './components/macro/TheHeader.vue'
import BaseMain from './components/macro/BaseMain.vue'
import TheFooter from './components/macro/TheFooter.vue'

export default {
  name: 'App',
  components: {
    TheHeader,
    BaseMain,
    TheFooter,
}
}
</script>

<style lang="scss">
</style>
