<template>
    <div class="search-box">
        <form @submit.prevent="$emit('search', searchText)">
            <input type="text" placeholder="Titolo film o serie TV" v-model="searchText">
            <button>Cerca</button>
        </form>
    </div>
</template>

<script>
export default {
    name: 'TheHeader',
    data() {
      return {
        searchText: ""
      }
    }
}
</script>

<style lang="scss" scoped>
</style> 