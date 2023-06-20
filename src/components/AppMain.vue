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
            searched: this.searchCards(),
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
                .get(`${this.apiURL}`)
                .then((response) => {
                    // handle success
                    console.log(response.data.data);
                    response.data.data.forEach((element, index) => {
                        if (
                            element.archetype !== undefined &&
                            !this.ArchetypeList.includes(element.archetype)
                        ) {
                            this.ArchetypeList.push(element.archetype);
                        }
                    });

                    console.log(this.ArchetypeList);
                })
                .catch(function (error) {
                    // handle error
                    console.log(error);
                });
        },
        sortArchetypes(archetype = "") {
            axios
                .get(`${this.apiURL}&archetype=${archetype}`)
                .then((response) => {
                    // handle success
                    this.CardsList = [];
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
        setTimeout(() => {
            this.searchCards();
            this.getArchetypes();
        }, 3000);
    },
};
</script>

<style lang="scss" scoped></style>
