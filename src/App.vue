<template>
    <div id="app">
        <ingredients></ingredients>
    </div>
</template>

<script>
import Ingredients from './components/Ingredients.vue';

export default {
    components: { Ingredients }
}
</script>

<style>
@import url(https://fonts.googleapis.com/css?family=Lato:400,100,300,700);
body {
    font-family: Lato;
    background: #F0F0F0;
}
</style>
