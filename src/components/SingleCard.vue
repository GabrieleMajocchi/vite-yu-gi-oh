<script>
    export default {
        name: 'SingleCard',
        props: {
            cardName: String,
            cardImg: String,
            cardArchetype: String,
        },
    }
</script>

<template>
    <div class="card rounded-0" style="width: 18rem;">
        <img :src="cardImg" class="card-img-top rounded-0" alt="...">
        <div class="card-body">
            <h5 class="card-title">{{ cardName }}</h5>
            <p class="card-text">{{ cardArchetype }}</p>
        </div>
    </div>
</template>

<style lang="scss" scoped>
    @use '../styles/partials/mixing.scss' as *;
    @use '../styles/partials/variables.scss' as *;

    .card{
        text-align: center;
        background-color: #d48f38;
        border: none;
        div h5{
            color: white;
        }
        div p{
            font-size: 1.2rem;
        }
    }
</style>
