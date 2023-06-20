<template>
    <div class="card">
        <div class="img-container">
            <div class="inner-content">
                <div class="front">
                    <img :src="image" :alt="name + ' card'" />
                </div>
                <div class="back">
                    <img src="../../assets/back.jpg" alt="back of the card" />
                </div>
            </div>
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
    width: calc(100% / 5 - 1rem);
    margin: 1rem 0.5rem;
    background-color: rgb(214, 155, 112);
    box-shadow: rgba(50, 50, 93, 0.25) 0px 6px 12px -2px,
        rgba(0, 0, 0, 0.3) 0px 3px 7px -3px;
    border: 1px solid rgb(180, 136, 105);
    transition: scale 1s;
    position: relative;
    z-index: 1;
}
.card:hover {
    scale: 1.2;
    position: relative;
    z-index: 2;
}
.img-container,
.inner-content,
.front {
    width: 100%;
}
.img-container {
    perspective: 1000px;
    height: 272px;
}
.inner-content {
    position: relative;
    height: 100%;
    transition: transform 0.5s;
    transform-style: preserve-3d;
}
.img-container:hover .inner-content {
    transform: rotateY(180deg);
    transition-delay: 0.3s;
}
.front,
.back {
    position: absolute;
    width: 100%;
    height: 100%;

    backface-visibility: hidden;
}
.back {
    transform: rotateY(180deg);
}
.desc-box {
    color: rgb(255, 255, 255);
}

img {
    width: 100%;
    border-radius: 0.375rem;
}
</style>
