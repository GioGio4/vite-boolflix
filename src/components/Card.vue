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
        <div class="vote-star">
            <!-- Dividi il voto per 2 e arrotonda Crea un ciclo per stampare le stelle al posto dei numeri  -->
            <img v-for="n in Math.ceil(vote / 2)" key="n" src="../assets/star-solid.svg" alt="iconStar">
            <!-- Crea un ciclo e stampa le stelle mancanti sottraendo il n. di stelle piene a 5 -->
            <img v-for="n in (5 - Math.ceil(vote / 2))" key="n" src="../assets/star-regular.svg" alt="iconStar">
        </div>
        <p>{{ Math.ceil(vote / 2) }}</p>
    </div>
</template>

<style lang="scss" scoped>
// Debug style
.card-layout {
    border: 1px solid red;
    width: calc(10% - 20px);
    margin: 0 10px;

    img {
        width: 15px;
        height: 15px
    }

    ;
}
</style>
