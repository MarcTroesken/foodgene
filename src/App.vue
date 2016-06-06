<template>
    <div id="app" class="container-fluid">
        <div class="row">
            <ingredient-preview
                :selected.sync="selected"
                :mix.sync="mix"
            ></ingredient-preview>

            <my-mix :mix.sync="mix"></my-mix>
        </div>

        <ingredients
            :selected.sync="selected"
            :mix.sync="mix"
        ></ingredients>
    </div>
</template>

<script>
import Ingredients from './components/Ingredients.vue';
import IngredientPreview from './components/IngredientPreview.vue';
import MyMix from './components/MyMix.vue';

export default {
    data() {
        return {
            selected: '',
            mix: []
        }
    },

    components: { Ingredients, IngredientPreview, MyMix }
}
</script>

<style lang="sass" src="../dist/sass/style.scss"></style>
