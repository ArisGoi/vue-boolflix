<template>
    <div class="card-container">

        <img class="poster" :src="`https://image.tmdb.org/t/p/w500${element.poster_path}`" :alt="element.title || element.name" @error="replaceSRC">

        <div class="card-info">

            <h3>{{element.title || element.name}}</h3>
            <h4>{{element.original_title || element.original_name}}</h4>
            <p>
                <span>Lingua:</span>
                <img width="50px" :src="`https://unpkg.com/language-icons/icons/${element.original_language}.svg`" :alt="`${element.original_language}`">
            </p>


            <p>
                <span>Voto:</span>
                <i class="fas fa-star" v-for="(starF, index) in getStars(element.vote_average)" :key="index"></i>
                <i class="far fa-star" v-for="(starF, index) in 5 - getStars(element.vote_average)" :key="index"></i>
            </p>

            <p class="overview">{{element.overview}}</p>

        </div>
    </div>
</template>

<script>
export default {
    name: "Card",
    props:['element'],
    components: {
    },
    methods:{
        getStars(vote10){
            let vote5 = Math.floor(vote10 * 5 / 10);
            return vote5
        },
        replaceSRC(e){
            e.target.src = 'https://mir-s3-cdn-cf.behance.net/project_modules/fs/9556d16312333.5691dd2255721.jpg'
        }
    }
}
</script>

<style scoped lang="scss">
@import '../assets/variables.scss';

.card-container{
    position: relative;
    height: 350px;
    color: white;
    margin-left: 20px;
    overflow: hidden;

    &:hover .card-info{
        opacity: 1;
    }

    .card-info{
        position: absolute;
        opacity: 0;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        display: flex;
        flex-direction: column;
        align-items: center;
        text-align: center;
        background: rgba($color: #000000, $alpha: 0.8);
        padding: 0 20px;

        & > *{
            margin-top: 15px;
        }
        h4{
            margin-top: 3px;
            opacity: 0.6;
        }

        i{
            color: #FFB12A;
        }

        p{
            display: flex;
            align-items: center;

            span{
                margin-right: 10px;
            }

            img{
                height: 30px;
                width: 30px;
                border-radius: 50%;
                border: 1px solid white;
            }
        }

        .overview{
            flex-grow: 1;
            font-size: .75rem;
        }
    }

    img.poster{
        height: 100%;
    }
}

</style>