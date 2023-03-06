<template>
    <li class="cardElement">
        <img :src="card.card_images[0].image_url" alt="">
        <h4>{{ card.name }}</h4>
        <span>{{ card.archetype }}</span>
    </li>
</template>

<script>

export default {
    props: {
        // PASSO L'OGGETTO INTERO COME PROP
        card: {
            type: Object,
            required: true
        },
    }
}

</script>

<style lang="scss" scoped>
.cardElement {
    width: fit-content;
    background-color: #d48f38;

    display: flex;
    flex-direction: column;
    justify-content: space-between;
    align-items: center;

    font-family: Arial, Helvetica, sans-serif;

    gap: 30px;
    padding-bottom: 30px;
}

.cardElement h4 {
    color: white;
    font-size: 18px;
}

.cardElement span {
    font-size: 18px;
}

img {
    width: 280px;
}
</style>