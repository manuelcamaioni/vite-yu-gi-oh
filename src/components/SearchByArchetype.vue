<template>
    <select class="form-select" aria-label="Default select example">
        <option>Open this select menu</option>
        <option v-for="(archetype, index) in ArchetypeList" :value="index + 1">
            {{ archetype }}
        </option>
    </select>
</template>

<script>
export default {
    data() {
        return {};
    },
    props: {
        ArchetypeList: Array,
    },
    mounted() {
        // setTimeout(() => {
        //     console.log(this.CardsList, "originale");
        // }, 5000);
    },
};
</script>

<style lang="scss" scoped></style>
