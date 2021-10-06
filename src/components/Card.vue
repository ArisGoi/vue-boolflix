<template>
    <div class="container">
        <img :src="`https://image.tmdb.org/t/p/w300${element.poster_path}`" alt="">
        <h3>{{element.title}}</h3>
        <h4>{{element.original_title}}</h4>
        <p>Lingua Originale: {{element.original_language}}</p>
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