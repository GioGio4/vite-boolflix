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
    <div class="row g-3 card-box ">
        <Card v-if="store.filmSearchedList != ''" v-for="film in store.filmSearchedList" :pic="film.poster_path"
            :title="film.title" :originalTitle="film.original_title" :language="film.original_language"
            :vote="film.vote_average" :overview="film.overview" />
    </div>
</template>

<style lang="scss"></style>