<script>
import axios from 'axios';
import pokeCard from './pokeCard.vue';
import typeSelect from './select.vue';

export default {
    name: 'mainApp',
    components: { pokeCard, typeSelect },
    data() {
        return {
            pokemons: [],

        }
    },
    methods: {
        onTypeChange(tipo) {
            console.log(tipo)
            axios.get(`https://41tyokboji.execute-api.eu-central-1.amazonaws.com/dev/api/v1/pokemons?per=20&eq[type1]=${tipo}`)
                .then((res) => {
                    this.pokemons = res.data.docs

                })
        }
    },


}

</script>
<template>
    <main>
        <div class="main-container mx-auto">
            <h2 class="text-center text-danger">CHOOSE YOUR TYPE HERE!</h2>
            <typeSelect @type-change="onTypeChange"></typeSelect>
            <div class="row">
                <pokeCard v-for="pokemon in pokemons" :key="pokemon.number" class="mb-5" :name="pokemon.name"
                    :image="pokemon.imageUrl" :number="pokemon.number">
                </pokeCard>
            </div>
        </div>
    </main>
</template>
<style scoped lang="scss">
main {
    height: 100vh;
    background-image: url(../assets/img/Johto_HGSSmap-1038x576.png);
    background-repeat: no-repeat;
    background-size: cover;
    padding-top: 106px;
    overflow-y: scroll;

    div {
        width: 1000px;
    }

}
</style>





