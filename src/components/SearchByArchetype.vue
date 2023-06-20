<template>
    <section>
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
    </section>
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
section {
    width: 100%;

    label {
        color: #3f3f3f;
        display: block;
        text-align: center;
    }
}

select {
    width: 30%;
    margin: 0.2rem auto 1rem;
}
</style>
