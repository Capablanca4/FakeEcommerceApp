<template>
    <div class="card">
        <h3> {{title }} </h3>
        <nuxt-link v-bind:to="link" class="card__img">
            <img v-bind:src="img" alt="The images was not found" />
        </nuxt-link>
        <nuxt-link v-bind:to="link" class="card__link">
            See also
        </nuxt-link>
    </div>
</template>

<script>
export default {
    props:{
        title: {
            type: String,
            default: "",
        },
        img:{
            type: String,
            default: "",
        },
        link:{
            type: String,
            default: "",
        }
    }
}
</script>

<style lang="scss" scoped>

@import './assets/sass/variables';

h3{
    padding: 10px;
}

.card{
    position: relative;
    width: 400px;
    height: 420px;
    background-color: $limon-Color;

    &__img{
        padding: 10px;
        width: 100%;

        & > img{
            width: 95%;
        }
    }

    &__link{
        position: absolute;
        bottom: 20px;
        left: 20px;
    }
}
</style>