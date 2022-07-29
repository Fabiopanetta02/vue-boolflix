<template>
  <div class="header">
    <!-- logo -->
    <div class="logo">
      <img src="../../assets/img/boolflix.png" alt="The Boolflix logo">
    </div>

    <!-- navbar -->
    <ul class="navabar">
      <li>Home</li>
      <li>Serie TV</li>
      <li>Film</li>
      <li>Nuovi e popolari</li>
      <li>La mia lista</li>
      <li>Audio e sottotitoli</li>
    </ul>

    <!-- searchbox -->
    <form @submit.prevent="$emit('search', searchText)">
        <input type="text" placeholder="Titolo film o serie TV" v-model="searchText" class="input">
        <button class="button">Cerca</button>
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
@import '../../assets/scss/style.scss';
@import '../../assets/scss/vars.scss';

img {
  height: 50px;
}

.input  {
  width: 250px;
  height: 30px;
  padding: 0 5px;
  margin-right: 10px;
  color: #fff;
  border: 2px solid red;
  border-radius: 5px;
  background-color: $background-dark;
}

.button {
  height: 30px;
  padding: 0 5px;
  color: $text-white;
  background-color: $background-red;
  border: none;
  border-radius: 5px;
}
</style> 