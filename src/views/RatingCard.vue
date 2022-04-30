<template>
      <div class="logo-container">
        <img class="circle-bgn" src="../assets/images/icon-star.svg" alt="">
      </div>
      <article class="card-description">
            <h3 class="description-heading">How did we do?</h3>
            <p class="description-para">
                Please let us know how we did with your support request. All feddback is appreciated to help us improve our offering!
            </p>
        </article>
      <form @submit.prevent="handleSubmit" class="card-rating-form">
            <section class="radio-input-container">
                <input type="radio" value="1" name="ratingNumber" v-model="ratingNumber">

                <input type="radio" value="2" name="ratingNumber" v-model="ratingNumber">
                    
                <input type="radio" value="3" name="ratingNumber" v-model="ratingNumber">
                    
                <input type="radio" value="4" name="ratingNumber" v-model="ratingNumber">
                    
                <input type="radio" value="5" name="ratingNumber" v-model="ratingNumber">

                <div class="errorModal" v-if="errorMsg">
                    <p>{{errorMsg}}</p>
                </div>
            </section>
            <button type="submit">SUBMIT</button>
      </form>
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
                this.$emit("rating-number", this.ratingNumber);
            }

        }
    }
}
</script>

<style lang="scss">
@import "../assets/scss/globals.scss";

.description-heading {
    color: $white;
    font-size: 2rem;
    padding: 1rem 0;
}

.description-para {
    color: $light-grey;
    line-height: 1.5rem;
}

.logo-container {
    display: flex;
    align-items: center;

    .circle-bgn {
        background: $round-bgn-form;
        padding: 1rem;
        border-radius: 50%;
    }
}

.card-rating-form {
    display: flex;
    flex-direction: column;
    gap: 1.25rem;

    button {
        width: 100%;
        margin: 0 auto;
        padding: 0.6rem 0;
        border-radius: 3rem;
        outline: none;
        border: none;
        font-weight: 700;
        color: $white;
        background: $orange;
        cursor: pointer;
        letter-spacing: 2px;

        &:hover {
            color: $orange;
            background: $white;
        }
    }
}

.radio-input-container {
    position: relative;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 0.5rem 0;

    input{
        appearance: none;
        width: 2.8rem;
        height: 2.8rem;
        display: block;
        margin: auto 0;
        background: $round-bgn-form;
        border-radius: 50%;
        display: flex;
        justify-content: center;
        align-items: center;
        cursor: pointer;

        &::after{
            color: $light-grey;
        }

        &:nth-child(1)::after{
            content: "1"
        }
        &:nth-child(2)::after{
            content: "2"
        }
        &:nth-child(3)::after{
            content: "3"
        }
        &:nth-child(4)::after{
            content: "4"
        }
        &:nth-child(5)::after{
            content: "5"
        }

        &:hover {
            background-color: $light-grey;
            color: $white;

            &::after{
                color: $white;
            }
        }

        &:checked {
            background-color: $orange;
            
            &::after{
                color: $white;
            }
        }
    }
}


.errorModal {
    position: absolute;
    top: -1.25rem;
    left: 0;
    right: 0;
    color: $red;
    font-weight: 700;
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 0.25rem;
    border-radius: 0.25rem;
}

</style>