<template>
  <RatingCard />
</template>

<script>
import RatingCard from './components/RatingCard.vue'

export default {
  name: 'App',
  components: {
    RatingCard
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


</style>
