<template>
  <section class="card rating-card">
      <div class="round-background">
        <img src="../assets/images/icon-star.svg" alt="">
      </div>
      <h3 class="heading-3">How did we do?</h3>
      <p class="main-p">
          Please let us know how we did with your support request. All feddback is appreciated to help us improve our offering!
      </p>
      <form @submit.prevent="handleSubmit" class="card-rating-form">
          <section class="checkbox-container">
              <div class="checkbox-wrapper">
                  <label class="main-p" >1
                    <input type="radio" value="1">
                  </label>
              </div>
                <div class="checkbox-wrapper">
                    <label class="main-p" >2</label>
                <input type="checkbox" value="2">
              </div>
              <div class="checkbox-wrapper">
                  <label class="main-p" >3</label>
                <input type="checkbox" value="3">
              </div>
              <div class="checkbox-wrapper">
                  <label class="main-p" >4</label>
                <input type="checkbox" value="4">
              </div>
              <div class="checkbox-wrapper">
                  <label class="main-p" >5</label>
                <input type="checkbox" value="5">
              </div>
          </section>
        <button type="submit">SUBMIT</button>
      </form>
  </section>
</template>

<script>
export default {
    data() {
        return {
            ratingValue: 0
        }
    },
    methods: {
        handleSubmit(e) {
            console.log("submit", e);
        }
    }
}
</script>

<style lang="scss">
@import "../assets/scss/globals.scss";

.card {
    width: clamp(270px, 200px + 30vw, 400px);
    background: $dark-blue;
    padding: 2rem;
    border-radius: 2rem;
}

.heading-3 {
    color: $white;
}

.main-p {
    color: $light-grey;
}

.card-rating-form {
    display: flex;
    flex-direction: column;
}

.round-background {
    background-color: $round-bgn-form;
    display: flex;
    width: 10%;
    display: flex;
    justify-content: center;
    padding: 1rem;
    border-radius: 50%;
}


.checkbox-wrapper{
    position: relative;
    display: flex;
    justify-content: center;
    align-items: center;
    background: $round-bgn-form;
    border-radius: 50%;



}

.checkbox-container {
    display: flex;
    justify-content: space-around;
    height: 2rem;
    margin: 2rem 0;
}

</style>