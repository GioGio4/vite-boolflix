<script>

export default {
    props: {
        pic: String,
        title: String,
        seriestitle: String,
        originalTitle: String,
        seriesOriginalTitle: String,
        language: String,
        vote: Number,
        overview: String,
    }
}

</script>

<template>
    <div class="col-2 card-layout p-1">
        <div class="cards">
            <img class="poster-img" :src="'https://image.tmdb.org/t/p/w342' + pic" alt="">
            <div class=" card-display">
                <p>{{ title || seriestitle }}</p>
                <p>{{ originalTitle || seriesOriginalTitle }}</p>
                <p>{{ language }}</p>
                <div class="vote-star d-flex">
                    <!-- Dividi il voto per 2 e arrotonda Crea un ciclo per stampare le stelle al posto dei numeri  -->
                    <img v-for="n in Math.ceil(vote / 2)" key="n" src="../assets/star-solid.svg" alt="iconStar">
                    <!-- Crea un ciclo e stampa le stelle mancanti sottraendo il n. di stelle piene a 5 -->
                    <img v-for="n in (5 - Math.ceil(vote / 2))" key="n" src="../assets/star-regular.svg" alt="iconStar">
                </div>
                <p><small>{{ overview }}</small></p>
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped>
// Debug style

.card-layout {
    border: 1px solid transparent;
}

.cards {
    background-color: black;
    width: 100%;
    height: 100%;

    .card-display {
        color: white;
        padding: 1rem;
        height: 100%;
    }

}


.card-layout:hover .poster-img {
    display: none;
}

.card-display {
    display: none;
}

.card-layout:hover .card-display {
    display: block;
    border: 1px solid white;
}




.poster-img {
    width: 100%;
    height: 100%;
}

.vote-star {
    width: 15px;
    height: 15px;
}
</style>
