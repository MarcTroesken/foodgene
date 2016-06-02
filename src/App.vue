<template>
    <div id="app">
        <ingredient-preview :selected.sync="selected"></ingredient-preview>
        <ingredients :selected.sync="selected"></ingredients>

        <pre>
            {{ $data | json }}
        </pre>
    </div>
</template>

<script>
import Ingredients from './components/Ingredients.vue';
import IngredientPreview from './components/IngredientPreview.vue';

export default {
    data() {
        return {
            selected: ''
        }
    },

    components: { Ingredients, IngredientPreview }
}
</script>

<style lang="sass" src="../dist/sass/style.scss"></style>
