<template>
    <div class="cover">
        <img src="https://image.tmdb.org/t/p/w342/hQq8xZe5uLjFzSBt4LanNP7SQjl.jpg">
        <div class="inner">
                <h2>{{title}}</h2>
                <h3>Titolo Originale: {{original_title}}</h3>
                <h4>Lingua: {{original_language}}</h4>
                <h3>Voto: {{vote_average}}</h3>
            </div>
    </div>
</template>

<script>
    export default {
        name:'Card',
        props:{
        original_title:String,
        title:String,
        original_language:String,
        vote_average:Number,
    },
    }
</script>

<style lang="scss" scoped>
.inner{
    h2,h2,h3,h4{
        color: white;
    }
}
</style>