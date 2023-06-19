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
    background-color: olivedrab;
    padding: 2rem 0;
}
</style>
