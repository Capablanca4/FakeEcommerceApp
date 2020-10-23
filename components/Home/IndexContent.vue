<template>
    <div class="content">
        <Card v-for="card in listCard" v-bind:key="card.id" :img="card.img" :link="card.link" :title="card.title" class="content__element" /> 
    </div>
</template>

<script>
import Card from '../Card.vue';

export default {
    components:{
        Card
    },
    data(){

        return {
            listCard:[
                {
                    id:1,
                    img:"/home-office.png",
                    link:"/Store/categories/1",
                    title:"Shop by Categories"
                },
                {
                    id:2,
                    img:"/home-office.png",
                    link:"/Store/categories/2",
                    title:"Greatest hit"
                },
                {
                    id:3,
                    img:"/home-office.png",
                    link:"/Store/categories/3",
                    title:"Promotions"
                },
                {
                    id:4,
                    img:"/home-office.png",
                    link:"/Store/categories/4",
                    title:"Test"
                },
                {
                    id:5,
                    img:"/home-office.png",
                    link:"/Store/categories/1",
                    title:"Shop by Categories"
                },
                {
                    id:6,
                    img:"/home-office.png",
                    link:"/Store/categories/2",
                    title:"Greatest hit"
                },
                {
                    id:7,
                    img:"/home-office.png",
                    link:"/Store/categories/3",
                    title:"Promotions"
                },
                {
                    id:8,
                    img:"/home-office.png",
                    link:"/Store/categories/4",
                    title:"Test"
                }
            ]
        }
    }
}
</script>

<style lang="scss" scoped>
.content{
    display: flex;
    flex-wrap: wrap;
    padding: 2vh 2vh 2vh 2vh;
    width: 100%;
    background-color: #f6f2df;

    &__element{
        margin: 20px;
    }
}
</style>