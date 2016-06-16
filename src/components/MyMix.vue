<template>
    <div class="col-lg-4 col-md-4 col-sm-12 hidden-xs">
        <div class="Mix-Container">
            <div class="Mix__Matching">
                <h1 class="Mix__Match">55%</h1>
                <p>Match of your ingredients.</p>
            </div>
            <div class="Mix__List">
                <ul v-if="mix.length > 0">
                    <li v-for="ingredient in mix">
                        <img class="Mix__Image img-circle" :src="ingredient.image" alt="{{ ingredient.name }}">
                        <span class="Mix__List-Item">{{ ingredient.name }}</span>
                        <a
                            href="#"
                            class="delete"
                            @click.prevent="removeIngredient(ingredient)"
                        >
                            <span class="glyphicon glyphicon-trash" aria-hidden="true"></span>
                        </a>
                    </li>
                </ul>
                <p v-else><strong>Nothing in the mix yet!</strong></p>
            </div>
            <div class="Mix__Cart">
                <button
                    class="btn btn-success btn-block"
                    @click="addToCart"
                >
                    Add to cart
                </button>
            </div>
        </div>
    </div>
</template>

<script>
    import config from '../../config.js';
    export default {
        props: ['mix'],

        methods: {
            removeIngredient(ingredient) {
                this.mix.$remove(ingredient);
            },
            addToCart(event) {
                if(this.mix.length > 0) {
                    this.$http.post(config.cartUrl, this.mix)
                    .then(res => {
                        console.log(res.data);
                        this.mix = [];
                        event.srcElement.blur();
                    });
                }

                event.srcElement.blur();
            },
        }
    }
</script>