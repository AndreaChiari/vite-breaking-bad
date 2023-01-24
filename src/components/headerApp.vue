<script>
export default {
    name: 'headerApp'
}
</script>
<template>
    <header class="mx-auto d-flex justify-content-center">
        <img class="img-fluid" src="../assets/img/pokedex.png" alt="pokedex.png">
    </header>


</template>
<style scoped lang="scss">
header {
    background-image: url(../assets/img/pokeball.png);
    background-size: contain;
    height: 100px;
    margin-bottom: 25px;
    position: fixed;
    top: 0%;
    right: 0;
    left: 0;
}
</style>
