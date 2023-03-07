<script>
import { store } from "../data/store"

export default {
    data() {
        return {

            store,
        }
    },
    methods: {
        getFlag(country) {
            country = country.toUpperCase();
            return "https://flagsapi.com/" + country + "/flat/64.png"
        }
    }

};
</script>

<template>
    <div v-if="store.filmList.length">
        <h2>FILM:</h2>
        <ul v-for="film in store.filmList">
            <li>
                <img :src="getFlag(film.original_language)" alt="">
                <!-- {{ film.original_language }} -->
            </li>
            <li>TITOLO ORIGINALE: {{ film.original_title }}</li>
            <li>TITOLO: {{ film.title }}</li>
            <li>VOTO. {{ film.vote_average }}</li>
        </ul>
    </div>
    <div v-else="">INIZIA LA RICERCA</div>
</template>

<style lang="scss" scoped></style>