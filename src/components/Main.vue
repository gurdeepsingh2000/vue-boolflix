<template>
    <div class="body-container">
         <h1>ORIGINALI NETFLIX</h1>
         <div>
             <Card v-for="film in filmList" 
             :key="film.id" 
             :original_title="film.original_title"
            :title="film.title"
            :original_language="film.original_language"
            :vote_average="film.vote_average" />/>
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
        }
    }
</script>

<style lang="scss" scoped>
    .body-container{
    h1{
        color:white
    }
}
</style>