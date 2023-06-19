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
                this.cards = response.data.data;
            })
        },
    }
</script>

<template>
    <main>
        <Dropdown class="dropdown"/>
        <div class="yugiCards d-flex flex-wrap">
            <SingleCard v-for="card in cards" :cardName="card.name" :cardImg="card.card_images[0].image_url" :cardArchetype="card.archetype"/>
        </div>
    </main>
</template>

<style lang="scss" scoped>
    @use '../styles/partials/mixing.scss' as *;
    @use '../styles/partials/variables.scss' as *;

    main{
        background-color: #d48f38;
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
</style>
