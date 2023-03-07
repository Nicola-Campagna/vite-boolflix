<script>
import { store } from "../data/store"

import BaseCard from "./BaseCard.vue";

export default {
    data() {
        return {

            store,
        }
    },
    components: {
        BaseCard
    }
    // methods: {
    //     getFlag(country) {
    //         country = country.toUpperCase();
    //         return "https://flagsapi.com/" + country + "/flat/64.png"
    //     }
    // }

};
</script>

<template>
    <div v-if="store.filmList.length">
        <h2>FILM:</h2>
        <BaseCard v-for="film in store.filmList" :title="film.title" :originalTitle="film.original_title"
            :lang="film.original_language" :vote="film.vote_average" />
    </div>

    <!-- serie tv -->
    <div v-if="store.tvSerieList.length">
        <h2>SERIE TV:</h2>
        <BaseCard v-for="tvSerie in store.tvSerieList" :title="tvSerie.name" :originalTitle="tvSerie.original_name"
            :lang="tvSerie.original_language" :vote="tvSerie.vote_average" />
    </div>

    <h2 v-if="!store.filmList.length && !store.tvSerieList.length">
        INIZIA LA RICERCA
    </h2>
</template>

<style lang="scss"></style>