<script>
// import MyComponent

// SEARCHBAR
import SearchBar from "./components/SearchBar.vue";

// axios
import axios from "axios"



export default {
  data() {
    return {
      appname: "BOOLFIX",
      baseUri: "https://api.themoviedb.org/3",
      apiKey: "7a133e976acaa1dadd272f9136c06752",
      filmList: [],
    }
  },

  components: {
    // registro i compoknenti per utilizzarli
    SearchBar,

  },

  methods: {
    fetchMovies(query) {
      // console.log(query);
      axios

        .get(`${this.baseUri}/search/movie`, {

          params: {
            api_key: this.apiKey, query
          }
        })

        .then((response) => {
          console.log(response.data.results);
          this.filmList = response.data.results
        })

    },
  }


};
</script>

<template>
  <SearchBar :title="appname" @search="fetchMovies" />
  <h2>FILM:</h2>
  <ul v-for="film in filmList">
    <li>{{ film.original_title }}</li>
    <li>{{ film.title }}</li>
    <li>{{ film.vote_average }}</li>
    <li>{{ film.original_language }}</li>

  </ul>
</template>

<style lang="scss"></style>
