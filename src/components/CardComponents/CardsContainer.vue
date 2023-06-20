<template>
    <section class="loader-container" v-if="CardsList.length === 0">
        <LoaderComponent class="m-auto" />
    </section>

    <section class="list-of-cards" v-else>
        <div class="container">
            <div class="row">
                <div class="col-12">
                    <h2 class="found-cards px-3">
                        {{ this.CardsList.length }} matches
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

import { store } from "../../store.js";
export default {
    components: {
        SingleCard,
        LoaderComponent,
    },
    props: {
        CardsList: Array,
    },

    data() {
        return {
            store,
        };
    },
};
</script>

<style lang="scss" scoped>
section.loader-container {
    margin: 3rem auto;
    width: 70%;
    background-color: transparent;
}
section.list-of-cards {
    margin: 3rem auto;
    width: 70%;
    border: 1px solid rgb(146, 146, 146);
    border-radius: 0.5rem;
    background-color: rgb(153, 124, 124);
    h2.found-cards {
        background-color: rgb(63, 63, 63);
        margin: 0.5rem;
        color: rgb(207, 207, 207);
        padding: 0;
        border-radius: 0.5rem;
        box-shadow: rgba(50, 50, 93, 0.25) 0px 6px 12px -2px,
            rgba(0, 0, 0, 0.3) 0px 3px 7px -3px;
    }
}
.container {
    margin: auto;
}
</style>
