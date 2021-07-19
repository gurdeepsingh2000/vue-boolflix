<template>
    <div class="body-container">
        <h1>ORIGINALI NETFLIX</h1>
        <div class="columns-container">
         <div class="columns">
             <Card class="inner-card" v-for="film in filmList" 
             :key="film.id" 
             :original_title="film.original_title"
            :title="film.title"
            :original_language="film.original_language"
            :vote_average="film.vote_average" />/>
            </div>
        </div>
    </div>
</template>

<script>
import Card from "./Card.vue"
    export default {
        name:'Main',
        components:{
            Card
        },
        props:{
            filmList: Array
        },
    }

    
</script>

<style lang="scss" scoped>
    .body-container{
        .columns-container{
            display: flex;
            justify-content: center;
        }
    h1{
        color:white
    }
    .columns{
        display: flex;
        flex-wrap: wrap;
        max-width: 1600px;

        .inner-card{
            max-width: 400px;
            margin: 0 20px
        }
    }
}
</style>