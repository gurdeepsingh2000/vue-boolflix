<template>
    <div class="cover">
        <div class="inner">
            <img :src="completeSrc(image)" alt="prova">
            </div>
            <div class="description">
                <h2>{{title}}</h2>
                <h3>Titolo Originale: {{original_title}}</h3>
                <h4>Lingua: {{original_language}}</h4>
                <h3>Voto: {{vote_average}}</h3>
                <h4>Lingua: <img :src="FlagSrc(original_language)" alt="flag"></h4>
                <div class="star"><i v-for="n in 5" :key="n" class="fa-star" :class="n <= vote ? 'fas': 'far'"></i></div>
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
    .cover{
        color: rgba($color: #fff, $alpha: 1);
        background: black;
        width:50%;
    }

    .inner{
        height: 370px;
        position: relative;


        img{
            height: auto;
            width:100%
        }
        &:hover{
            opacity: 0.2;
            background: black;
            transition: .5s ease;
            color: white;
            height: 170px;
        }
    }

    

        h4:nth-child(5){
            img{
                margin-left: 10px;
                width: 40px;
            }
    }

    .star{
        color: yellow;
    }
</style>