<template>
    <div class="container">
        <ul class="holist">
            <li v-for="(film, index) in films" :key="index">
                <Card :element="film"/>
            </li>
        </ul>
    </div>
</template>

<script>
import Card from './Card.vue'
export default {
    name: "Films",
    components:{
        Card
    },
    props:['films']
}
</script>

<style scoped lang="scss">
@import '../assets/variables.scss';
@import '../assets/lists.scss';

</style>