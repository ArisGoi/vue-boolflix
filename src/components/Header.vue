<template>
    <header>
        <div class="container-l">
            <h1>BOOLFLIX</h1>
            <div>
                <input type="text" v-model="searchText">
                <button @click="$emit('search', searchText)">Cerca</button>
            </div>
        </div>
    </header>
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
@import '../assets/variables.scss';
    header{
        background-color: $c-bg-1;
        color: white;

        .container-l{
            display: flex;
            align-items: center;
            justify-content: space-between;
            height: $header-height;
        }
        
        h1{
            color: $c-main;
        }
    }
</style>