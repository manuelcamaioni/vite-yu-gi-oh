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
</style>
