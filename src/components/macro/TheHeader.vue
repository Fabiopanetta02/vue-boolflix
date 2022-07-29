<template>
  <div class="header">
    <div class="container">
      <div class="navbar">
        <!-- logo -->
        <div class="logo">
          <img src="../../assets/img/boolflix.png" alt="The Boolflix logo">
        </div>

        <!-- searchbox -->
        <form @submit.prevent="$emit('search', searchText)">
            <input type="text" placeholder="Titolo film o serie TV" v-model.trim="searchText" class="input">
            <button class="button">Cerca</button>
        </form>
      </div>
    </div>
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
.container{
  height: 100%;
}
.navbar{
    display: flex;
    justify-content: space-between;
    align-items: center;
    height: 100%;
}
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