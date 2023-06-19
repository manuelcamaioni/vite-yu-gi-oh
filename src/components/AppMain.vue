<template>
    <main>
        <CardsContainer />
    </main>
</template>

<script>
import CardsContainer from "./CardComponents/CardsContainer.vue";
export default {
    data() {
        return {};
    },
    components: {
        CardsContainer,
    },
};
</script>

<style lang="scss" scoped>
main {
    background-color: rgb(255, 144, 124);
}
</style>
