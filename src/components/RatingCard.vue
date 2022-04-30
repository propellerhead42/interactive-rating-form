<template>
  <section class="card rating-card">
      <div class="logo-container">

        <img class="circle-bgn" src="../assets/images/icon-star.svg" alt="">


      </div>
      <h3 class="heading-3">How did we do?</h3>
      <p class="main-p">
          Please let us know how we did with your support request. All feddback is appreciated to help us improve our offering!
      </p>
      <form @submit.prevent="handleSubmit" class="card-rating-form">
          <section class="checkbox-container">
              <div class="checkbox-wrapper">
                    <label class="main-p circle-bgn" >1
                    <input type="radio" value="1" name="ratingNumber" v-model="ratingNumber">
                    </label>
              </div>
              <div class="checkbox-wrapper">
                    <label class="main-p circle-bgn" >
                    <input type="radio" value="2" name="ratingNumber" v-model="ratingNumber">
                    </label>
              </div>
              <div class="checkbox-wrapper">
                    <label class="main-p circle-bgn" >3
                    <input type="radio" value="3" name="ratingNumber" v-model="ratingNumber">
                    </label>
              </div>
              <div class="checkbox-wrapper">
                    <label class="main-p circle-bgn" >4
                    <input type="radio" value="4" name="ratingNumber" v-model="ratingNumber">
                    </label>
              </div>
              <div class="checkbox-wrapper">
                    <label class="main-p circle-bgn" >5
                    <input type="radio" value="5" name="ratingNumber" v-model="ratingNumber">
                    </label>
              </div>
              <div class="errorModal" v-if="errorMsg">
                  <p>{{errorMsg}}</p>
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
            ratingNumber: null,
            errorMsg: ""
        }
    },
    methods: {
        handleSubmit() {
            if(this.ratingNumber == null){
                this.errorMsg = "Choose a number";
                return;
            } else {
                this.errorMsg = "";
                console.log("submit", this.ratingNumber);
            }

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
    display: flex;
    flex-direction: column;
    gap: 2rem;
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
    gap: 1rem;
}

.logo-container {
    padding: 1rem 0;
    display: flex;
    align-items: center;

    .circle-bgn {
        background: $round-bgn-form;
        padding: 1rem;
        border-radius: 50%;
    }
}

.checkbox-container {
    position: relative;
    display: flex;
    justify-content: space-around;
    align-items: center;
    padding-bottom: 2rem;
}

.checkbox-wrapper {
    position: relative;
    .circle-bgn {
        display: block;
        width: 3rem;
        height: 3rem;
        border-radius: 50%;
        display: flex;
        justify-content: center;
        align-items: center;
    }

    label {
        color: $white;
        z-index: 999;

        &:hover {
        }
    }

    input {
        position: absolute;
        appearance: none;
        width: 100%;
        height: 100%;
        border-radius: 50%;
        cursor: pointer;
        background-color: $round-bgn-form;

        &::after {
            position: relative;
            content: " ";
            display: flex;
            justify-content: center;
            align-items: center;
            width: 100%;
            height: 100%;
        }
        
        &:hover {
            background-color: $light-grey;
        }

        &:checked{
            background-color: $orange;
        }

    }
}

.errorModal {
    position: absolute;
    bottom: 0;
    left: 0;
    right: 0;
    background: rgb(164, 19, 19);
    color: $white;
    font-weight: 700;
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 0.25rem;
    border-radius: 0.25rem;
}

</style>