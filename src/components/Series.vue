<template>
    <div class="container">
        <h1>SERIES</h1>
        <ul>
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

</style>