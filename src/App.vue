<template>
  <section class="card-wrapper">

  </section>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {

  }
}
</script>

<style lang="scss">
// Global styles

// Reset:
*{
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: 'Overpass', sans-serif;
  
  p{
    font-size: 15px;
  }

}

input,
button,
select,
a {
  font: inherit
}

// Variabels:
$orange: hsl(25, 97%, 53%);

$white: hsl(0, 0%, 100%);
$light-grey: hsl(217, 12%, 63%);
$medium-grey: hsl(216, 12%, 54%);
$dark-blue: hsl(213, 19%, 18%);
$very-dark-blue: hsl(216, 12%, 8%);


#app { }


</style>
