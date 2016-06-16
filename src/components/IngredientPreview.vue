<template>
    <div class="col-lg-8 col-md-8 col-sm-12 col-xs-12">
         <div class="Preview-Container">
            <div class="Preview__Image">
                <img class="img-responsive img-circle" :src="selected.image" alt="Image">
            </div>
            <div class="Preview__Match visible-xs">
                <h2>55%</h2>
                <span class="text-muted">matching</span>
            </div>
            <div class="Preview__Text">
                <h2>{{ selected.name }}</h2>
                <p>{{ selected.description }}</p>
            </div>
            <button
                class="btn btn-success"
                @click="addToMix(selected, $event)"
                v-if="inMix(selected)"
            >
                Add to mix
            </button>
            <button
                class="btn btn-danger"
                @click="removeFromMix(selected, $event)"
                v-if="! inMix(selected)"
            >
                Remove from mix
            </button>
        </div>
    </div>
</template>

<script>
    import config from '../../config.js';
    export default {
        props: ['selected', 'mix'],

        methods: {
            addToMix(ingredient, event) {
                if(this.mix.indexOf(ingredient) == -1) {
                    this.mix.push(ingredient);
                    event.srcElement.blur();
                }
            },
            removeFromMix(ingredient, event) {
                this.mix.$remove(ingredient);
                event.srcElement.blur();
            },
            inMix(ingredient) {
                if(this.mix.indexOf(ingredient) == -1) {
                    return true;
                }
            }
        }
    }
</script>