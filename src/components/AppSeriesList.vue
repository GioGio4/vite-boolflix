<script>
import Card from './Card.vue';
import { store } from "../Data/Store";

export default {
    data() {
        return {
            store,
        }
    },
    components: { Card }
}

</script>

<template>
    <!-- Layout provvisorio!! -->

    <div class="row g-3">
        <Card v-if="store.seriesSearchedList != ''" v-for="serietv in store.seriesSearchedList" :pic="serietv.poster_path"
            :seriestitle="serietv.name" :seriesOriginalTitle="serietv.original_name" :language="serietv.original_language"
            :vote="serietv.vote_average" :overview="serietv.overview" />
    </div>
</template>

<style lang="scss"></style>