<script>
import axios from 'axios';

export default {
    name: 'typeSelect',
    data() {
        return {
            types: [],

        }
    },
    methods: {
        getType() {
            axios.get('https://41tyokboji.execute-api.eu-central-1.amazonaws.com/dev/api/v1/pokemons/types1')
                .then((res) => {
                    this.types = res.data
                });

        },
    }

}






</script>


<template>
    <select class="select">
        <option class="option" v-for="element in types"></option>
    </select>
</template>


<style>
select {
    width: 200px;
    margin-left: 420px;
}
</style>






