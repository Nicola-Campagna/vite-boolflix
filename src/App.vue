<script>
// import MyComponent

// SEARCHBAR
import SearchBar from "./components/SearchBar.vue";

// axios
import axios from "axios"

// appmain
import AppMain from "./components/AppMain.vue";

// store
import { store } from "./data/store"



export default {
  data() {
    return {
      appname: "BOOLFIX",
      baseUri: "https://api.themoviedb.org/3",
      apiKey: "7a133e976acaa1dadd272f9136c06752",
    }
  },

  components: {
    // registro i compoknenti per utilizzarli
    SearchBar,
    AppMain

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
          store.filmList = response.data.results
        })

    },
  }


};
</script>

<template>
  <SearchBar :title="appname" @search="fetchMovies" />
  <AppMain />
</template>

<style lang="scss"></style>
