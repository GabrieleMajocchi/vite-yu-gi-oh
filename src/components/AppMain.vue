<script>
    import Dropdown from './DropDown.vue';
    import SingleCard from './SingleCard.vue';
    import axios from 'axios';
    export default {
        name: 'AppMain',
        components: {
            Dropdown,
            SingleCard,
        },
        data() {
            return {
                cards: [],
            }
        },
        created() {
            axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0')
            .then((response)=>{
                setTimeout(()=>{
                    this.cards = response.data.data;
                }, 2500);
            })
        },
    }
</script>

<template>
    <div class="loader" v-if="cards.length === 0">
        <img src="../assets/img/loading-yugioh.gif" alt="loader gif">
    </div>

    <main v-else>
        <Dropdown class="dropdown"/>
        <div class="yugiCards d-flex flex-wrap">
            <div class="foundedCards w-100 fw-bold d-flex align-items-center p-3">
                <p class="m-0">Found {{cards.length}} cards</p>
            </div>
            <SingleCard v-for="card in cards" :cardName="card.name" :cardImg="card.card_images[0].image_url" :cardArchetype="card.archetype" :cardEbay="card.card_prices[0].ebay_price"/>
        </div>
    </main>
</template>

<style lang="scss" scoped>
    @use '../styles/partials/mixing.scss' as *;
    @use '../styles/partials/variables.scss' as *;

    main{
        background-color: #d48f38;
    }

    .foundedCards{
        background-color: #212529;
        color: white;
    }
    .dropdown{
        margin-left: 12rem;
        margin-top: 2rem;
    }
    .yugiCards{
        margin: auto;
        display: flex;
        flex-wrap: wrap;
        gap: 2rem;
        background-color: white;
        padding: 3rem;
        margin-top: 2rem;
        width: 1670px;
    }

    .loader img{
        width: 100vw;
        height: calc(100vh - 57.5px);
    }
</style>
