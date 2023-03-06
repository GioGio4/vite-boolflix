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
    <div class="d-flex">
        <Card v-if="store.seriesSearchedList != ''" v-for="serietv in store.seriesSearchedList" :seriestitle="serietv.name"
            :seriesOriginalTitle="serietv.original_name" :language="serietv.original_language"
            :vote="serietv.vote_average" />
    </div>
</template>

<style lang="scss"></style>