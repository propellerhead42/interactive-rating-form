<template>
<section class="card" v-if="!successSubmit">
    <RatingCard @rating-number="getRatingNumber"/>
</section>
  <section class="card" v-else>
    <AppreciationCard :ratingNumber="ratingNumber"/>
</section>
</template>

<script>
import AppreciationCard from './views/AppreciationCard.vue'
import RatingCard from './views/RatingCard.vue'


export default {
  name: 'App',
  emits: ['rating-number'],
  components: {
    RatingCard,
    AppreciationCard
  },
  data() {
    return {
      successSubmit: false,
      ratingNumber: null
    }
  },
  methods: {
    getRatingNumber(num){
      this.ratingNumber = num;
      this.successSubmit = true;
    }
  }
}
</script>

<style lang="scss">
// Global styles

@import "../src/assets/scss/globals.scss";


#app {
  width: 100vw;
  height: 100vh;
  background-color: rgb(242, 242, 242);
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: $very-dark-blue;
}

.card {
    width: clamp(270px, 200px + 30vw, 400px);
    min-height: 425px;
    background: $dark-blue;
    padding: 2rem;
    border-radius: 2rem;
    display: flex;
    flex-direction: column;
    gap: 1.5rem;
}



</style>
