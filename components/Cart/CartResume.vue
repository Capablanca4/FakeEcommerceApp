<template>
    <div class="resume">
        <div v-if="products.length == 0" class="resume__empty">
            Cart is empty
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

<style lang="sass" scoped>

</style>