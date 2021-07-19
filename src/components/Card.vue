<template>
    <div class="cover">
        <div class="inner">
            <img :src="completeSrc(image)" alt="prova">
                <h2>{{title}}</h2>
                <h3>Titolo Originale: {{original_title}}</h3>
                <h4>Lingua: {{original_language}}</h4>
                <h3>Voto: {{vote_average}}</h3>
                <h4>Lingua: <img class="flag" :src="FlagSrc(original_language)" alt="flag"></h4>
            </div>
    </div>
</template>

<script>
    export default {
        name:'Card',
        props:{
        image:String,
        original_title:String,
        title:String,
        original_language:String,
        vote_average:Number,
    },

       methods:{
           completeSrc(partialSrc){
               return `http://image.tmdb.org/t/p/w500/${partialSrc}`
           },
           FlagSrc(CountryLanguage){
               return require('../assets/' + CountryLanguage + '.svg')
           }
       }
    }

</script>

<style lang="scss" scoped>
.inner{
    h2,h2,h3,h4{
        color: white;
    }
}
</style>