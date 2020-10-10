<template>
    <div class="card">
        <h3> {{title }} </h3>
        <nuxt-link v-bind:to="link" class="card__img">
            <img v-bind:src="img" />
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

<style scoped>
.card{
    position: relative;
    width: 400px;
    height: 420px;
    background-color: var(--limon-Color);
}

h3{
    padding: 10px;
}

.card__img{
    padding: 10px;
    width: 100%;
}

.card__img > img{
    width: 95%;
}

.card__link{
    position: absolute;
    bottom: 20px;
    left: 20px;
}

</style>