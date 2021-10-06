<template>
    <div class="container">
        <img :src="`https://image.tmdb.org/t/p/w300${element.poster_path}`" alt="">
        <h3>{{element.title}}{{element.name}}</h3>
        <h4>{{element.original_title}}{{element.original_name}}</h4>
        <!-- <p>Lingua Originale: {{element.original_language}}</p> -->
        <img width="50px" :src="`https://unpkg.com/language-icons/icons/${element.original_language}.svg`" :alt="`${element.original_language}`">
        <!-- <p>Voto: {{`${getStars(element.vote_average)}`}}</p> -->
        <p>
            Voto:
            <i class="fas fa-star" v-for="(starF, index) in getStars(element.vote_average)" :key="index"></i>
            <i class="far fa-star" v-for="(starF, index) in 5 - getStars(element.vote_average)" :key="index"></i>
        </p>
    </div>
</template>

<script>
export default {
    name: "Card",
    props:['element'],
    methods:{
        getStars(vote10){
            let vote5 = Math.floor(vote10 * 5 / 10);
            return vote5
        }
    }
}
</script>

<style scoped lang="scss">

</style>