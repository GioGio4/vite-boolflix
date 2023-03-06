<script>

export default {
    props: {
        title: String,
        seriestitle: String,
        originalTitle: String,
        seriesOriginalTitle: String,
        language: String,
        vote: Number,
    }
}

</script>

<template>
    <div class="card-layout d-flex flex-column">
        <p>{{ title || seriestitle }}</p>
        <p>{{ originalTitle || seriesOriginalTitle }}</p>
        <p>{{ language }}</p>
        <p>{{ vote }}</p>
    </div>
</template>

<style lang="scss" scoped>
// Debug style
.card-layout {
    border: 1px solid red;
    width: calc(10% - 20px);
    margin: 0 10px;
}
</style>