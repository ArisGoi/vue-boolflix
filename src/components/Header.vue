<template>
    <div class="container">
        <input type="text" v-model="searchText">
        <button @click="$emit('search', searchText)">Cerca</button>
    </div>
</template>

<script>
export default {
    name: "Header",
    data() {
        return{
            searchText: "",
        }
    }
}
</script>

<style scoped lang="scss">

</style>