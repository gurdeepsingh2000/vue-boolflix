<template>
    <div class="cover">
        <div class="inner">
            <img :src="completeSrc(image)">
            <div class="description">
                <h2>{{title}}</h2>
                <h3>Titolo Originale: {{original_title}}</h3>
                <h4>Lingua: {{original_language}}</h4>
                <h3>Voto: {{vote_average}}</h3>
                <h4>Lingua: <img :src="FlagSrc(original_language)" alt="flag"></h4>
                <div class="star"><i v-for="n in 5" :key="n" class="fa-star" :class="n <= vote ? 'fas': 'far'"></i></div>
            </div>
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
    data() {
        return {
            vote: Math.round(this.vote_average /2)
        }
    },
    
    
       methods:{
           completeSrc(partialSrc){
               return `http://image.tmdb.org/t/p/w500/${partialSrc}`
           },
           FlagSrc(CountryLanguage){
                if(CountryLanguage === "en") {
                    return require('../assets/' + 'us' + '.svg')
                }
                else if(CountryLanguage === "sv"){
                        return require('../assets/' + 'se' + '.svg')
                }
                
                else{
                    return require('../assets/' + CountryLanguage + '.svg')
                }
           }
       }
    }
</script>

<style lang="scss" scoped>
    .description{
            width: 500px;
            height: 100%;
            position: absolute;
            top: 2%;
            padding: 50% 50px;
            opacity: 0;

            &:hover{
                transition: ease-in-out 0.4s;
                opacity: 1;
                background: rgba($color: #000000, $alpha: 0.8);
                color:white
            }
        h4 img{
            width: 40px ;
        }
        .star{
            color: yellow;
        }
    }
</style>