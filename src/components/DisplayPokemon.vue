<template>
    <div>
        <h1>Pokemon</h1>
        <section v-for="pokemon in pokemons" :key="pokemon[3]">
            <h2>{{pokemon[0]}}</h2>
            <img :src="pokemon[2]" alt="">
            <p>{{pokemon[1]}}</p>
        </section>
    </div>
</template>

<script>
import axios from "axios"
    export default {
        data() {
            return {
                pokemons: []
            }
        },
        mounted () {
            axios.request({
                url: `http://127.0.0.1:5000/api/pokemon`
            }).then((response) => {
                this.pokemons = response[`data`]
            }).catch((error) => {
                alert("Sorry, an error has occurred.")
                error
            });
        },
    }
</script>

<style scoped>

</style>