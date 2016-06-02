<template>
    <div class="Chooser">
        <div class="Category-Switch">
            <div class="two-thirds column">
                <ul class="Categories">
                    <li><a href="#">Kategorie 1</a></li>
                    <li><a href="#">Kategorie 2</a></li>
                    <li><a href="#">Kategorie 3</a></li>
                    <li><a href="#">Kategorie 4</a></li>
                    <li><a href="#">Kategorie 5</a></li>
                </ul>
            </div>
            <div class="one-third column">
                <div class="Search">
                    <input class="u-full-width" type="text" placeholder="Suche nach Zutat ...">
                </div>
            </div>
        </div>
        <div class="Ingredients">
            <a href="#" class="Ingredient">
                <img class="Ingredient__Image" src="http://placehold.it/100x100" alt="Placeholder">
                <br />
                <span class="Ingredient__Title">Zutat</span>
            </a>
            <a href="#" class="Ingredient">
                <img class="Ingredient__Image" src="http://placehold.it/100x100" alt="Placeholder">
                <br />
                <span class="Ingredient__Title">Zutat</span>
            </a>
            <a href="#" class="Ingredient">
                <img class="Ingredient__Image" src="http://placehold.it/100x100" alt="Placeholder">
                <br />
                <span class="Ingredient__Title">Zutat</span>
            </a>
            <a href="#" class="Ingredient">
                <img class="Ingredient__Image" src="http://placehold.it/100x100" alt="Placeholder">
                <br />
                <span class="Ingredient__Title">Zutat</span>
            </a>
            <a href="#" class="Ingredient">
                <img class="Ingredient__Image" src="http://placehold.it/100x100" alt="Placeholder">
                <br />
                <span class="Ingredient__Title">Zutat</span>
            </a>
            <a href="#" class="Ingredient">
                <img class="Ingredient__Image" src="http://placehold.it/100x100" alt="Placeholder">
                <br />
                <span class="Ingredient__Title">Zutat</span>
            </a>
            <a href="#" class="Ingredient">
                <img class="Ingredient__Image" src="http://placehold.it/100x100" alt="Placeholder">
                <br />
                <span class="Ingredient__Title">Zutat</span>
            </a>
            <a href="#" class="Ingredient">
                <img class="Ingredient__Image" src="http://placehold.it/100x100" alt="Placeholder">
                <br />
                <span class="Ingredient__Title">Zutat</span>
            </a>
            <a href="#" class="Ingredient">
                <img class="Ingredient__Image" src="http://placehold.it/100x100" alt="Placeholder">
                <br />
                <span class="Ingredient__Title">Zutat</span>
            </a>
            <a href="#" class="Ingredient">
                <img class="Ingredient__Image" src="http://placehold.it/100x100" alt="Placeholder">
                <br />
                <span class="Ingredient__Title">Zutat</span>
            </a>
            <a href="#" class="Ingredient">
                <img class="Ingredient__Image" src="http://placehold.it/100x100" alt="Placeholder">
                <br />
                <span class="Ingredient__Title">Zutat</span>
            </a>
            <a href="#" class="Ingredient">
                <img class="Ingredient__Image" src="http://placehold.it/100x100" alt="Placeholder">
                <br />
                <span class="Ingredient__Title">Zutat</span>
            </a>
            <a href="#" class="Ingredient">
                <img class="Ingredient__Image" src="http://placehold.it/100x100" alt="Placeholder">
                <br />
                <span class="Ingredient__Title">Zutat</span>
            </a>
            <a href="#" class="Ingredient">
                <img class="Ingredient__Image" src="http://placehold.it/100x100" alt="Placeholder">
                <br />
                <span class="Ingredient__Title">Zutat</span>
            </a>
            <a href="#" class="Ingredient">
                <img class="Ingredient__Image" src="http://placehold.it/100x100" alt="Placeholder">
                <br />
                <span class="Ingredient__Title">Zutat</span>
            </a>
        </div>
    </div>
</template>

<script>
    export default {

    }
</script>

<style>
    .input.u-full-width {
        margin-bottom: 0;
    }
    .Category-Switch {
        bottom: 176px;
        position: fixed;
        width: 100%;
    }
    .Categories {
        list-style: none;
        margin: 0;
        margin-left: 30px;
        padding: 0;
    }
    .Categories > li {
        display: inline-block;
        margin-right: 20px;
    }
    .Categories > li:last-child {
        margin-right: 0;
    }
    .Search {
        padding-right: 30px;
    }
    .Ingredients {
        width: 100%;
        max-height: 176px;
        border-top: 1px solid lightgrey;
        bottom: 0;
        position: fixed;
        background: #fff;
        overflow-x: scroll;
        overflow-y: hidden;
        padding: 30px 30px 15px 30px;
        white-space: nowrap;
    }
    .Ingredient {
        display: inline-block;
        text-align: center;
        width: 100px;
        margin-right: 20px;
    }
    .Ingredient:last-child {
        margin-right: 0;
    }
    .Ingredient__Image {
        width: 100px;
        height: 100px;
        margin: 0;
    }
    .Ingredient__Title {
        font-size: 15px;
        line-height: 15px;
    }
</style>