<script>
import AppFilmList from "./AppFilmList.vue";
import AppSeriesList from "./AppSeriesList.vue";



export default {

    components: { AppFilmList, AppSeriesList }
}
</script>

<template>
    <!-- Layout temporaneo sezione film e sezione serie tv -->
    <section class="film-list container my-4">
        <h2>Film</h2>
        <AppFilmList />
    </section>
    <section class="series-list container mb-5">
        <h2>Series</h2>
        <AppSeriesList />
    </section>
</template>

<style lang="scss"></style>
