<template>
    <div class="container">
        <label for="searchArch">Search by Archetype</label>
        <select
            name="searchArch"
            class="form-select"
            aria-label="Default select example"
            v-model="archetype">
            <option
                v-for="(archetype, index) in ArchetypeList"
                :value="archetype"
                @click="$emit('sort', archetype)">
                {{ archetype }}
            </option>
        </select>
    </div>
</template>

<script>
export default {
    data() {
        return {
            archetype: "",
        };
    },
    props: {
        ArchetypeList: Array,
    },
};
</script>

<style lang="scss" scoped>
label {
    color: #3f3f3f;
    margin: 0 1rem;
}
</style>
