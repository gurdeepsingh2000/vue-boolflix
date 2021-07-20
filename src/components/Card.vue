<template>
    <div class="cover">
        <div class="inner">
            <img :src="completeSrc(image)" alt="prova">
            </div>
                <h2>{{title}}</h2>
                <h3>Titolo Originale: {{original_title}}</h3>
                <h4>Lingua: {{original_language}}</h4>
                <h3>Voto: {{vote_average}}</h3>
                <h4>Lingua: <img :src="FlagSrc(original_language)" alt="flag"></h4>
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
                if(CountryLanguage === "en") {
                    return require('../assets/' + 'us' + '.svg')
                } else {
                    return require('../assets/' + CountryLanguage + '.svg')
                }
           }
       }
    }

</script>

<style lang="scss" scoped>
    .cover{
        color: white;
        position: relative;
    }

    .inner{
        position: relative;

        img{
            height: 700px;
        }
        &:hover{
            opacity: 0.2;
            background: black;
            transition: .5s ease;
            color: white;
        }
    }

    

        h4:nth-child(6){
            display: flex;
            align-items: center;
            img{
                margin-left: 10px;
                width: 40px;
            }
    }
</style>