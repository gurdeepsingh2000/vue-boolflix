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
            :vote_average="film.vote_average"
            :completeSrc="film.poster_path"
            :image="film.poster_path"
                />
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
        background: black;

        .columns-container{
            display: flex;

            .columns{
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            width:100%;

            .inner-card{
                width: calc(100% / 4 );
                height: 664px;
            }
    }
        }
    h1{
        color:white
    }

}
</style>