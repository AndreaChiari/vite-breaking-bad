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
            types: []
        }
    },


    created() {
        axios.get('https://41tyokboji.execute-api.eu-central-1.amazonaws.com/dev/api/v1/pokemons?per=10&page=22')
            .then((res) => {
                this.pokemons = res.data.docs
            })

    }, getType() {
        axios.get('https://41tyokboji.execute-api.eu-central-1.amazonaws.com/dev/api/v1/pokemons/types1')
            .then((res) => {
                this.types = res.data
                console.log(types)
            })
    },


}







</script>
<template>
    <main>
        <div class="main-container mx-auto">
            <div class="row">
                <pokeCard v-for="pokemon in pokemons" :key="pokemon.number" class="mb-5" :name="pokemon.name"
                    :image="pokemon.imageUrl" :number="pokemon.number">
                </pokeCard>
            </div>
            <typeSelect></typeSelect>
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

    div {
        width: 1000px;
    }

}
</style>