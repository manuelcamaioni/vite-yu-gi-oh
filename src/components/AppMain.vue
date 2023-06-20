<template>
    <main>
        <CardsContainer :CardsList="CardsList" />
    </main>
</template>

<script>
import CardsContainer from "./CardComponents/CardsContainer.vue";
import axios from "axios";
export default {
    data() {
        return {
            CardsList: [],
            apiURL: "https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0",
        };
    },
    components: {
        CardsContainer,
    },

    created() {
        axios
            .get(this.apiURL)
            .then((response) => {
                // handle success

                setTimeout(() => {
                    this.CardsList = response.data.data;
                }, 5000);
            })
            .catch(function (error) {
                // handle error
                console.log(error);
            });
    },
};
</script>

<style lang="scss" scoped></style>
