<script>
import { store } from "../data/store"

export default {
    data() {
        return {

            store,
        }
    }

};
</script>

<template>
    <div v-if="store.filmList.length">
        <h2>FILM:</h2>
        <ul v-for="film in store.filmList">
            <li>{{ film.original_title }}</li>
            <li>{{ film.title }}</li>
            <li>{{ film.vote_average }}</li>
            <li>{{ film.original_language }}</li>
        </ul>
    </div>
    <div v-else="">INIZIA LA RICERCA</div>
</template>

<style lang="scss" scoped></style>