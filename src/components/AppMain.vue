<script>
import AppFilmList from "./AppFilmList.vue";
import AppSeriesList from "./AppSeriesList.vue";



export default {

    components: { AppFilmList, AppSeriesList }
}
</script>

<template>
    <!-- Layout temporaneo sezione film e sezione serie tv -->
    <section class="film-list">
        <AppFilmList />
    </section>
    <section class="series-list">
        <AppSeriesList />
    </section>
</template>

<style lang="scss"></style>
