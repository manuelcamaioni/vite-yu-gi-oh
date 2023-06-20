<template>
    <main>
        <SearchByArchetype
            @sort="sortArchetypes"
            :ArchetypeList="ArchetypeList" />
        <CardsContainer :CardsList="CardsList" />
    </main>
</template>

<script>
import CardsContainer from "./CardComponents/CardsContainer.vue";
import axios from "axios";
import SearchByArchetype from "./SearchByArchetype.vue";
export default {
    data() {
        return {
            CardsList: [],
            ArchetypeList: [],
            apiURL: "https://db.ygoprodeck.com/api/v7/cardinfo.php?num=50&offset=0",
        };
    },
    methods: {
        searchCards() {
            axios
                .get(this.apiURL)
                .then((response) => {
                    // handle success

                    this.CardsList = response.data.data;
                })
                .catch(function (error) {
                    // handle error
                    console.log(error);
                });
        },
        getArchetypes() {
            axios
                .get(this.apiURL)
                .then((response) => {
                    response.data.data.forEach((element, index) => {
                        if (
                            element.archetype !== undefined &&
                            !this.ArchetypeList.includes(element.archetype)
                        ) {
                            this.ArchetypeList.push(element.archetype);
                        }
                    });
                })
                .catch(function (error) {
                    // handle error
                    console.log(error);
                });
        },
        sortArchetypes(archetype = "") {
            axios
                .get(this.apiURL, { params: { archetype: archetype } })
                .then((response) => {
                    // handle success

                    this.CardsList = response.data.data;
                })
                .catch(function (error) {
                    // handle error
                    console.log(error);
                });
        },
    },
    components: {
        CardsContainer,
        SearchByArchetype,
    },

    created() {
        this.searchCards();
        this.getArchetypes();
    },
};
</script>

<style lang="scss" scoped></style>
