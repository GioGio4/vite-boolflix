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
        <Card v-if="store.filmSearchedList != ''" v-for="film in store.filmSearchedList" :title="film.title"
            :originalTitle="film.original_title" :language="film.original_language" :vote="film.vote_average" />
    </div>
</template>

<style lang="scss"></style>