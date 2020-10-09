<template>
    <div class="content">
        <Card :img="'~assets/home-office.png'" :link="'/Store/categories/1'" :title="'Shop by Categories'" /> 
    </div>
</template>

<script>
import Card from '../Card.vue';

export default {
    components:{
        Card
    }
}
</script>

<style scoped>
.content{
    padding: 2vh 2vh 2vh 2vh;
    width: 100%;
    height: 500px;
    background-color: aqua;
}
</style>