<template>

<section class="appreciation-container">
  <div class="image-conatiner">
    <img src="@/assets/images/illustration-thank-you.svg" alt="Thank you illustration">
  </div>
  <div class="rating-container">
    <p>You selected {{ratingNumber}} out of 5</p>
  </div>
  <article class="card-description">
      <h3 class="description-heading">Thank you!</h3>
      <p class="description-para">
        We appreciate you taking the time to give a rating. If you ever need more support, don't hesitate to get in touch!
      </p>
  </article>
</section>


</template>

<script>
export default {
    props: ["ratingNumber"],
    data() {
      return {

      }
    }, methods: {

    }

}
</script>

<style lang="scss" scoped>
@import "./src/assets/scss/globals.scss";

.appreciation-container{
  display: flex;
  flex-direction: column;
  align-items: center;
}

.rating-container {
  margin-top: 1.5rem;
  margin-bottom: 1rem;
  padding: 0.6rem;
  border-radius: 1rem;
  background-color: $round-bgn-form;
  color: $orange;
  letter-spacing: 1.2px;
}

.description-heading {
    color: $white;
    font-size: 2rem;
    padding: 1rem 0;
}

.description-para {
    color: $light-grey;
    line-height: 1.5rem;
}

.card-description {
  text-align: center;
}



</style>