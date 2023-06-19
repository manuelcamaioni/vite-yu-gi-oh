<template>
    <header class="py-2">
        <div class="container-fluid">
            <div class="row">
                <div class="col-3">
                    <img
                        src="https://vignette1.wikia.nocookie.net/yugiohenespanol/images/a/aa/Yugioh_anime_logo.jpg/revision/latest?cb=20130310042737&path-prefix=es"
                        alt="" />
                </div>
                <div
                    class="col-6 d-flex justify-content-center align-items-center">
                    <h1>Yu-Gi-Oh API</h1>
                </div>
                <div class="col"></div>
            </div>
        </div>
    </header>
</template>

<script>
export default {
    data() {
        return {};
    },
};
</script>

<style lang="scss" scoped>
header {
    img {
        width: 100%;
        mix-blend-mode: multiply;
    }
    h1 {
        font-style: oblique;
        color: #3f3f3f;
    }
}
</style>
