<template>
    <AppHeader />
    <AppMain />
</template>

<script>
import AppHeader from "./components/AppHeader.vue";
import AppMain from "./components/AppMain.vue";
export default {
    data() {
        return {};
    },
    components: {
        AppHeader,
        AppMain,
    },
};
</script>

<style lang="scss">
@import "bootstrap/scss/bootstrap";
@import url("https://fonts.googleapis.com/css2?family=Cabin&family=Fira+Sans:ital,wght@0,500;0,600;1,400;1,500&family=Montserrat:wght@300;500;700&family=Open+Sans:ital,wght@0,300;0,700;0,800;1,500&family=PT+Sans:ital,wght@0,700;1,400&family=Roboto:wght@300;500;700&display=swap");

* {
    font-family: "Roboto", sans-serif;
}
div#app {
    background-color: rgb(255, 158, 141);
    padding-bottom: 2rem;
}
</style>
