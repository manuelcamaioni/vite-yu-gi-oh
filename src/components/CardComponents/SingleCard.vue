<template>
    <div class="card">
        <div class="img-container">
            <img :src="image" :alt="name + ' card'" />
        </div>
        <div class="desc-box text-center p-2">
            <h2 class="fs-5">{{ name }}</h2>
            <p>{{ archetype }}</p>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {};
    },
    props: {
        name: String,
        archetype: String,
        image: String,
    },
};
</script>

<style lang="scss" scoped>
.card {
    overflow: hidden;
    width: calc(100% / 5 - 1rem);
    margin: 1rem 0.5rem;
    .img-container {
        width: 100%;
        img {
            width: 100%;
        }
    }
}
</style>
