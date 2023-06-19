<template>
    <LoaderComponent v-if="CardsList.length === 0" />

    <section v-else class="card">
        <div class="container m-2">
            <div class="row">
                <div class="col-12">
                    <h2 class="found-cards px-3">
                        You found {{ this.CardsList.length }} cards
                    </h2>
                </div>
            </div>
        </div>
        <div class="container">
            <div class="row">
                <div class="col-12 d-flex flex-wrap">
                    <SingleCard
                        v-for="Card in CardsList"
                        :name="Card.name"
                        :archetype="Card.archetype"
                        :image="Card.card_images[0].image_url" />
                </div>
            </div>
        </div>
    </section>
</template>

<script>
import SingleCard from "./SingleCard.vue";
import LoaderComponent from "../LoaderComponent.vue";
import axios from "axios";
import { store } from "../../store.js";
export default {
    components: {
        SingleCard,
        LoaderComponent,
    },

    data() {
        return {
            store,
            CardsList: [],
        };
    },
    created() {
        axios
            .get(
                "https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0"
            )
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

<style lang="scss" scoped>
LoaderComponent {
    width: 100%;
}
section {
    margin: auto;
    width: 70%;
    background-color: white;
    h2.found-cards {
        background-color: rgb(63, 63, 63);
        margin: 0.5rem;
        color: rgb(207, 207, 207);
        padding: 0;
        border-radius: 0.5rem;
    }
}
.container {
    margin: auto;
}
</style>
