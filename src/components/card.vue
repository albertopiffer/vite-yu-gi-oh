<template>
    <li class="cardElement">
        <img :src="card.card_images[0].image_url" alt="">
        {{ card.id }}
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
}

img {
    width: 280px;
}
</style>