<script>


export default {
    name: 'typeSelect',
    data() {
        return {
            types: [
                "Psychic",
                "Ice",
                "Grass",
                "Ghost",
                "Water",
                "Ground",
                "Bug",
                "Flying",
                "Fire",
                "Fairy",
                "Normal",
                "Dragon",
                "Steel",
                "Electric",
                "Poison",
                "Fighting",
                "Rock",
                "Dark"
            ],
            categoryType: '',
            emits: ['type-change'],

        }
    },
    /* methods: {
        getType() {
            axios.get('https://41tyokboji.execute-api.eu-central-1.amazonaws.com/dev/api/v1/pokemons/types1')
                .then((res) => {
                    console.log(res)
                    this.types = res.data
                });
        },

    },
    created() {
        this.getType()
    }
    */



}
</script>

<template>
    <select class="select" @change="$emit('type-change', categoryType)" v-model="categoryType">
        <option class="option" v-for="element in types" :key="element.types">{{
            element
        }}</option>
    </select>
</template>


<style>
select {
    width: 200px;
    margin-left: 390px;
}
</style>













