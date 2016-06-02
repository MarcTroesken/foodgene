<template>
    <div class="Chooser">
        <div class="Category-Switch">
            <div class="col-md-8">
                <ul class="Categories">
                    <li v-for="category in categories">
                        <a href="#" @click="selectCategtory(category)">{{ category.name }}</a>
                    </li>
                </ul>
            </div>
            <div class="col-md-4">
                <div class="Search">
                    <input
                        class="form-control"
                        type="text"
                        v-model="query"
                        placeholder="Suche nach Zutat ..."
                    />
                </div>
            </div>
        </div>
        <div class="Ingredients">
            <a
                href="#"
                class="Ingredient"
                @click="selectIngredient(ingredient)"
                v-for="ingredient in ingredients | filterBy query"
            >
                <img class="Ingredient__Image" src="{{ ingredient.image }}" alt="{{ ingredient.name }}">
                <br />
                <span class="Ingredient__Title">{{ ingredient.name }}</span>
            </a>
        </div>
    </div>
</template>

<script>
    import config from '../../config.js';
    export default {
        props: ['selected'],

        data() {
            return {
                query: '',
                category: '',
                ingredients: [],
                categories: []
            }
        },

        ready() {
            this.getCategories();
        },

        methods: {
            getCategories() {
                // this.$http.get(config.categoriesUrl).then(res => {
                //     this.categories = res.data;
                //     this.category = this.categories[0];
                //     this.ingredients = this.categories[0].ingredients;
                // });

                // Fake data
                this.categories = [
                    {id: 1, name: 'Kategorie 1', ingredients: [
                        {id: 1, image: 'http://placehold.it/150x150', name: 'Zutat 1'},
                        {id: 2, image: 'http://placehold.it/150x150', name: 'Zutat 2'},
                        {id: 3, image: 'http://placehold.it/150x150', name: 'Zutat 3'},
                        {id: 4, image: 'http://placehold.it/150x150', name: 'Zutat 4'},
                        {id: 5, image: 'http://placehold.it/150x150', name: 'Zutat 5'},
                        {id: 6, image: 'http://placehold.it/150x150', name: 'Zutat 6'},
                        {id: 7, image: 'http://placehold.it/150x150', name: 'Zutat 7'},
                        {id: 8, image: 'http://placehold.it/150x150', name: 'Zutat 8'},
                        {id: 9, image: 'http://placehold.it/150x150', name: 'Zutat 9'}
                    ]},
                    {id: 2, name: 'Kategorie 2', ingredients: [
                        {id: 1, image: 'http://placehold.it/150x150', name: 'Schinken 1'},
                        {id: 2, image: 'http://placehold.it/150x150', name: 'Schinken 2'},
                        {id: 3, image: 'http://placehold.it/150x150', name: 'Schinken 3'},
                        {id: 4, image: 'http://placehold.it/150x150', name: 'Schinken 4'},
                        {id: 5, image: 'http://placehold.it/150x150', name: 'Schinken 5'},
                        {id: 6, image: 'http://placehold.it/150x150', name: 'Schinken 6'},
                        {id: 7, image: 'http://placehold.it/150x150', name: 'Schinken 7'},
                        {id: 8, image: 'http://placehold.it/150x150', name: 'Schinken 8'},
                        {id: 9, image: 'http://placehold.it/150x150', name: 'Schinken 9'}
                    ]},
                    {id: 3, name: 'Kategorie 3'},
                    {id: 4, name: 'Kategorie 4'},
                    {id: 5, name: 'Kategorie 5'},
                    {id: 6, name: 'Kategorie 6'}
                ];

                this.category = this.categories[0];
                this.ingredients = this.categories[0].ingredients;
            },
            selectIngredient(ingredient) {
                this.selected = ingredient;
            },
            selectCategtory(category) {
                this.category = category;
                this.ingredients = category.ingredients;
            }
        }
    }
</script>