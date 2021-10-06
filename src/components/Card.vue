<template>
    <div class="container">
        <img :src="`https://image.tmdb.org/t/p/w300${element.poster_path}`" alt="">
        <h3>{{element.title}}{{element.name}}</h3>
        <h4>{{element.original_title}}{{element.original_name}}</h4>
        <!-- <p>Lingua Originale: {{element.original_language}}</p> -->
        <img width="50px" :src="`https://unpkg.com/language-icons/icons/${element.original_language}.svg`" :alt="`${element.original_language}`">
        <p>Voto: {{element.vote_average}}</p>
    </div>
</template>

<script>
export default {
    name: "Card",
    props:['element']
}
</script>

<style scoped lang="scss">

</style>