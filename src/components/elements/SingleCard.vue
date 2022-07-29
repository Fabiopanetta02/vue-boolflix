<template>
  <div class="card">
    <img v-if="!info.poster_path" src="https://ancasadental.com/wp-content/uploads/2020/09/dentalia-placeholder-img-4-750x750.jpg" alt="`${info.original_title || info.original_name}`" class="default-img">
    <img v-else :src="`https://image.tmdb.org/t/p/w342/${info.poster_path}`" alt="`${info.original_title || info.original_name}`">
    <div class="card-hover">
      <h2>{{info.title || info.name}}</h2>
      <h5>{{info.original_title || info.original_name}}</h5>
      <div class="flags">
        <img v-if="flags.includes(info.original_language)" :src="require(`../../assets/img/${info.original_language}.png`)" :alt="info.original_language" class="flag-nation">
        <img v-else src="../../assets/img/none.png" alt="Flag not available" class="flag-other">
      </div>
      <div class="ratings">
        <div class="grey-stars">
          <div v-for="rating in 5" :key="rating">
            <i class="fas fa-star"></i>
          </div>
        </div>

        <div class="yellow-stars">
          <div v-for="stars in starRating" :key="stars">
            <i class="fas fa-star"></i>
          </div>
        </div>
      </div>
      <p class="overview">{{info.overview}}</p>
    </div>
    
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
    },
    computed: {
      starRating() {
        return Math.ceil(this.info.vote_average / 2);
      }
    }
}
</script>

<style lang="scss" scoped>
@import '../../assets/scss/vars';
.card{
  text-align: center;
  position: relative;

  img{
      max-width: 100%;
      height: 500px;
      }

  .card-hover {
    padding: 20px 10px;
    height: 500px;
    position: absolute;
    top: 0;
    left: 0;
    bottom: 0;
    right: 0;
    opacity: 0;
    background-color: rgba(0, 0, 0, 0.8);
    display: flex;
    flex-direction: column;
    gap: 18px;
    overflow-y: scroll;
  }
  .card-hover:hover {
    opacity: 1;
  }

  .flags {
    img.flag-nation {
      width: 50px;
      height: 25px;
      margin-bottom: 10px;
    }
    img.flag-other {
      width: 50px;
      height: 50px;
      margin-bottom: 10px;
    }
  }

  .ratings {
    display: flex;
    position: relative;
    justify-content: center;
    .grey-stars {
      display: flex;
      color: $text-grey;
      font-size: 20px;
    }
    .yellow-stars {
      display: flex;
      position: absolute;
      font-size: 20px;
      top: 0;
      left: 93px;
      z-index: 1;
      color: $text-yellow;
    }
  }
}

</style>