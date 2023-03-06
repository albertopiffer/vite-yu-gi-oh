<template>
    <main>
        <div>

            <ul class="cardsList">
                <Card v-for="element in store.cards" :key="element.id" :card="element" />
                <!-- <img :src="card.card_images[0].image_url" alt=""> -->
            </ul>

        </div>
    </main>
</template>

<script>

import axios from 'axios'

import store from '../store'

import Card from './card.vue'

export default {
    components: {
        Card
    },
    data() {
        return {
            store,
        }
    },
    computed: {
        cards() {
            return this.store.cards
        }
    },
    methods: {
        fetchCards() {

            axios
                .get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0')
                .then((res) => {
                    this.store.cards = res.data.data
                })

        }
    },
    created() {
        this.fetchCards()
    },
}

</script>

<style lang="scss" scoped>
main {
    padding: 125px 160px;
    background-color: #d48f38;
}

main .cardsList {
    padding: 70px;
    background-color: white;

    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;

}
</style>