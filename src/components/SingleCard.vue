<script>
    export default {
        name: 'SingleCard',
        props: {
            cardName: String,
            cardImg: String,
            cardArchetype: String,
            cardEbay: String,
        },
    }
</script>

<template>
    <div class="flip-card">
	<div class="card rounded-0 flip-card-inner" style="width: 18rem;">
        <div class="flip-card-front">
            <img :src="cardImg" class="card-img-top rounded-0" alt="...">
            <div class="card-body">
                <h5 class="card-title">{{ cardName }}</h5>
                <p class="card-text">{{ cardArchetype }}</p>
            </div>
        </div>
        <div class="flip-card-back">
            <img src="../assets/img/cardback.jpg" alt="back of the card">
            <div class="card-body">
                <p class="card-text">Price on ebay: {{cardEbay}}</p>
            </div>
        </div>
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

    .flip-card {
        background-color: transparent;
        width: 288px;
        height: 540px;
        perspective: 1000px;
    }

    .flip-card-inner {
        position: relative;
        width: 100%;
        height: 100%;
        text-align: center;
        transition: transform 0.6s;
        transform-style: preserve-3d;
        box-shadow: 0 4px 8px 0 rgba(0,0,0,0.2);
    }

    .flip-card:hover .flip-card-inner {
        transform: rotateY(180deg);
    }

    .flip-card-front, .flip-card-back {
        position: absolute;
        width: 100%;
        height: 100%;
        -webkit-backface-visibility: hidden;
        backface-visibility: hidden;
    }

    .flip-card-front {
        background-color: #d48f38;
        color: black;
    }

    .flip-card-back {
        background-color: #d48f38;
        color: white;
        transform: rotateY(180deg);
        box-shadow: 0 0 0 0 ;
        img{
            width: 100%;
        }
    }
    
</style>
