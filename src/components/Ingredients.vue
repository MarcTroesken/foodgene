<template>
    <div class="Chooser">
        <div class="row Category-Switch">
            <div class="col-lg-12 col-md-12 col-sm-12 col-xs-12">
                <div class="row">
                    <div class="col-lg-8 col-md-8 col-sm-8 col-xs-12">
                        <ul class="Categories">
                            <li v-for="category in categories">
                                <a href="#" @click="selectCategtory(category, $event)">{{ category.name }}</a>
                            </li>
                        </ul>
                    </div>
                    <div class="col-lg-4 col-md-4 col-sm-4 col-xs-12">
                        <div class="Search form-group">
                            <input
                                class="form-control"
                                type="text"
                                v-model="query"
                                placeholder="Search for ingredients ..."
                            />
                        </div>
                    </div>
                </div>
            </div>
        </div>
        <div class="Ingredients">
            <a
                href="#"
                class="Ingredient clearfix"
                :class="inMix(ingredient) ? 'selected' : ''"
                @click="selectIngredient(ingredient)"
                v-for="ingredient in ingredients | filterBy query"
            >
                <img class="Ingredient__Image" :src="ingredient.image" alt="{{ ingredient.name }}">
                <br />
                <span class="Ingredient__Title">{{ ingredient.name }}</span>
            </a>
        </div>
    </div>
</template>

<script>
    import config from '../../config.js';
    // import Stub from '../../stubs.js';
    export default {
        props: ['selected', 'mix'],

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
                this.$http.get(config.categoriesUrl).then(res => {
                    console.log('Ingredient: ' + res.data);
                    this.categories = res.data;
                    this.category = this.categories[0];
                    this.ingredients = this.categories[0].ingredients;
                    this.selected = this.ingredients[0];
                });

                // Fake Data !!
                // this.categories = Stub.categories;
                // this.category = this.categories[0];
                // this.ingredients = this.categories[0].ingredients;
                // this.selected = this.ingredients[0];
            },
            selectIngredient(ingredient) {
                this.selected = ingredient;
            },
            selectCategtory(category, event) {
                this.category = category;
                this.ingredients = category.ingredients;
                event.srcElement.blur();
            },
            inMix(ingredient) {
                if(this.mix.indexOf(ingredient) > -1) {
                    return true;
                }
            }
        }
    }
</script>