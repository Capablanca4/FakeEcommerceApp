<template>
    <div class="resume">
        <div v-if="products.length == 0" class="resume__empty">
            <img src="/empty-cart.png" alt="the image was not found" class="empty__img"/>
            <h1 class="empty__title">Your cart is empty</h1>
            <div class="empty__suggestions">
                No Idea ?<br/>
                Get a look at our suggestion below.
            </div>
        </div>
        <div v-else class="resume__notEmpty">
            Cart is not empty
        </div>
    </div>
</template>

<script>
export default {
    data(){
        return {
            products:[],
        }
    }
}
</script>

<style lang="scss" scoped>

@import './assets/sass/variables';

.resume__empty{
    display: grid;
    grid-template-areas: 
    "image title . . . . ."
    "image suggestions . . . . .";
    background-color: $limon-Color;
    border-radius: 5px;
    margin: 0 auto;
    height: 400px;
    width: 98%;
}

.empty{

    &__suggestions{
        grid-area: suggestions;
        background-color: $limon-Color-darker;
        border-radius: 15px;
        padding: 1em;
        width: 50%;
        height: 100px;
        font-weight: bold;
    }

    &__img{
        grid-area: image;
        align-self: center;
        margin: 0 auto;
        width: 250px;
        height: 375px;
    }

    &__title{
        grid-area: title;
        align-self: center;
        font-size: 30px;
    }
}
</style>