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
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}
</style>
