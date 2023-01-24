<script>
import axios from 'axios';
import pokeCard from './pokeCard.vue';

export default {
    name: 'mainApp',
    components: { pokeCard },
    data() {
        return {
            pokemons: []

        }

    },
    created() {
        axios.get('https://41tyokboji.execute-api.eu-central-1.amazonaws.com/dev/api/v1/pokemons?per=10&page=1')
            .then((res) => { this.pokemons = res.data.results; })

    }
}




</script>
<template>
    <main>
        <div class="container">
            <div class="row col-lg2 col-md-3 col-sm-4 g-4">
                <pokeCard v-for="pokemon in pokemons" :key="pokemon.number" class="mb-5" :name="pokemon.name"
                    :image="pokemon.image" :number="pokemon.number">


                </pokeCard>
            </div>
        </div>
    </main>
</template>
<style>
main {
    height: 100vh;
    background-image: url(../assets/img/Johto_HGSSmap-1038x576.png);
    background-repeat: no-repeat;
    background-size: cover;
}
</style>