<template>
    <div class="card-wrapper">
        <img class="my-card" src="../assets/front-exodia.jpg" alt="" />
        <img class="my-card card-back" src="../assets/back.jpg" alt="" />
    </div>
</template>

<script>
export default {
    data() {
        return {};
    },
};
</script>

<style lang="scss" scoped>
@keyframes cardFlip {
    0% {
        transform: rotateY(0deg);
    }
    50% {
        transform: rotateY(180deg);
    }
    100% {
        transform: rotateY(0deg);
    }
}

.card-wrapper {
    position: relative;
    transform-style: preserve-3d;
    animation: cardFlip 3s ease-in-out infinite;
    width: 100px;
    height: 150px;
    border-radius: 0.375rem;
}
.my-card {
    position: absolute;
    backface-visibility: hidden;
    width: 100px;
    height: 150px;
}

.card-back {
    transform: rotateY(180deg);
}
</style>
