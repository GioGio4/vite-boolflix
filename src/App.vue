<script>
import AppMain from "./components/AppMain.vue";
import AppHeader from "./components/AppHeader.vue";
import axios from "axios";
import { store } from "./Data/Store";

export default {
  data() {
    return {
      store,
    }
  },

  components: { AppMain, AppHeader },

  methods: {
    // Al click o al rilascio del tasto invio vengono svuotate le liste nello store, poi viene 
    // richiamato axios aggiungendo il "tearm" dopo la query= (API)
    search(tearm) {
      store.filmSearchedList = [],
        store.seriesSearchedList = [],

        // Lista film cercati
        axios.get(("https://api.themoviedb.org/3/search/movie?api_key=3ad2b809de5ceef6ec6bd710fdbb1aab&language=it-IT&query=") + (tearm))
          .then((response) => {
            store.filmSearchedList = response.data.results
          })

      // Lista serie tv cercate
      axios.get(("https://api.themoviedb.org/3/search/tv?api_key=3ad2b809de5ceef6ec6bd710fdbb1aab&language=it-IT&query=") + (tearm))
        .then((response) => {
          store.seriesSearchedList = response.data.results
        })

    }

  },
}

</script>

<template>
  <AppHeader @on-search="search" />
  <AppMain />
</template>

<style lang="scss"></style>
