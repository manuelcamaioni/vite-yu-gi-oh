<template>
    <div class="card">
        <div class="img-container">
            <img :src="image" :alt="name + ' card'" />
        </div>
        <div class="desc-box text-center p-2">
            <h2 class="fs-5">{{ name }}</h2>
            <p class="mb-0">{{ archetype }}</p>
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
    background-color: rgb(214, 155, 112);
    box-shadow: rgba(50, 50, 93, 0.25) 0px 6px 12px -2px,
        rgba(0, 0, 0, 0.3) 0px 3px 7px -3px;
    border: 1px solid rgb(180, 136, 105);
    .desc-box {
        color: rgb(255, 255, 255);
    }
    .img-container {
        width: 100%;
        img {
            width: 100%;
            border-radius: 0.375rem;
        }
    }
}
</style>
