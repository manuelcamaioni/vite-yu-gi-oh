<template>
    <select
        class="form-select"
        aria-label="Default select example"
        v-model="archetype">
        <option>Search by Archetype</option>
        <option
            v-for="(archetype, index) in ArchetypeList"
            :value="archetype"
            @click="$emit('sort', archetype)">
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
};
</script>

<style lang="scss" scoped></style>
