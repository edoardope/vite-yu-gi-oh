<script>
export default {
    name: "SingleCard",
    props: {
        dettagliCarta: Object,
        cindex: Number
    },

    data() {
        return {

        };
    },
    created() {

    },
    methods: {

    }
};
</script>

<template>
    <div>
        <img :src="dettagliCarta.card_images[0].image_url" alt="">
        <br>
        <span class="text-white h5">{{ dettagliCarta.name }}</span>
        <br>
        <span>{{ dettagliCarta.type }}</span>
    </div>
</template>

<style lang="scss" scoped>
div {
    text-align: center;
    flex-basis: calc(90% / 3);
    margin-bottom: 10px;
    background-color: orange;

    span {
        display: inline-block;
        margin: 10px;
    }

    img {
        width: 100%;
    }
}
</style>