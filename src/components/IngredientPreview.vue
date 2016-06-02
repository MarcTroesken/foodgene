<template>
    <div class="col-md-7">
        <div class="Preview-Container">
            <div class="Preview__Image">
                <img class="img-responsive" src="http://placehold.it/300x300" alt="Image">
            </div>
            <div class="Preview__Text">
                <h3>{{ selected.name }}</h3>
                <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Quibusdam esse adipisci quisquam impedit rerum ab aperiam obcaecati? Quaerat dolor impedit perferendis aut blanditiis, dolore earum vel debitis fugiat alias quibusdam!</p>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        props: ['selected']
    }
</script>