<template>
    <div class="container">
        <ul class="holist">
            <li v-for="(serie, index) in series" :key="index">
                <Card :element="serie"/>
            </li>
        </ul>
    </div>
</template>

<script>
import Card from './Card.vue'
export default {
    name: "Series",
    components:{
        Card
    },
    props:['series']
}
</script>

<style scoped lang="scss">
@import '../assets/variables.scss';
@import '../assets/lists.scss';

</style>