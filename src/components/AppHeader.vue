<script>

export default {
    data() {
        return {
            userSearch: "",
        };
    },

    emits: ["on-search"],

    // Al click sul bottone "invia" viene passato quello che è inserito nel "userSearch" al genitore (in questo caso una stringa
    // che contiene la ricerca dell'utente)
    methods: {
        search() {
            this.$emit("on-search", this.userSearch)
        }
    }

}

</script>

<template>
    <nav class="navbar navbar-dark bg-dark">
        <div class="container-fluid">
            <a class="navbar-brand text-danger fw-bold">BOOLFLIX</a>
            <form @submit.prevent="">
                <div class="input-group">
                    <input v-model="userSearch" type="text" class="form-control" placeholder="Cerca..."
                        aria-label="Cerca..." aria-describedby="button-addon2" @keyup.enter="search">
                    <button class="btn btn-outline-secondary" type="button" @click="search">Cerca</button>
                </div>
            </form>
        </div>
    </nav>
</template>

<style lang="scss"></style>
