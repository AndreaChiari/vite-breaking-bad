<script>

export default {
    name: 'pokeCard',
    props: {
        name: String,
        image: String,
        number: Number,
    }
}
</script>
<template>
    <div class='p-2'>
        <img class="img-fluid" :src=image :alt=name>
        <h3>{{ name }} #{{ number }}</h3>
    </div>

</template>



<style scoped>
div {
    flex-basis: calc(100% / 5);

}

h3 {
    color: rgb(211, 55, 48);
}
</style>