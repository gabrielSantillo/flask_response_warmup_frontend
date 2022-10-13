<template>
    <div>
        <display-pokemon></display-pokemon>
        <insert-pokemon></insert-pokemon>
    </div>
</template>

<script>
import DisplayPokemon from './DisplayPokemon.vue'
import InsertPokemon from './InsertPokemon.vue'
    export default {
  components: { DisplayPokemon, InsertPokemon },
        
    }
</script>

<style scoped>

</style>