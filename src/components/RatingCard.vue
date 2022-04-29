<template>
  <section class="card rating-card">
      <img src="../assets/images/icon-star.svg" alt="">
      <h3 class="heading-3">How did we do?</h3>
      <p class="main-p">
          Please let us know how we did with your support request. All feddback is appreciated to help us improve our offering!
      </p>
      <form>
        <input type="checkbox" class="main-p" value="1">
        <input type="checkbox" class="main-p" value="2">
        <input type="checkbox" class="main-p" value="3">
        <input type="checkbox" class="main-p" value="4">
        <input type="checkbox" class="main-p" value="5">
        <button type="submit">SUBMIT</button>
      </form>

  </section>
</template>

<script>
export default {

}
</script>

<style lang="scss">
@import "../assets/scss/globals.scss";

.card {
    width: clamp(200px, 25%, 30%);
    background: red;
}

.heading-3 {
    color: $white;
}

</style>