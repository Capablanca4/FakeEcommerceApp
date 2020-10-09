<template>
    <div>
        <h3> {{title }} </h3>
        <img v-bind:src="img" />
        <nuxt-link v-bind:to="link">
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