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
    fetchResults(term) {
      this.fetchFilm(term);
      this.fetchTvSerie(term);

    },

    fetchFilm(query) {
      // chiamata axios per film
      axios
        .get(`${this.baseUri}/search/movie`, {

          params: {
            api_key: this.apiKey, query
          }
        })

        .then((response) => {
          // console.log(response.data.results);
          store.filmList = response.data.results
        })
    },

    fetchTvSerie(query) {
      // chiamata axios per serie tv
      axios.get(`${this.baseUri}/search/tv`, {

        params: {
          api_key: this.apiKey, query
        }
      })

        .then((response) => {
          // console.log(response.data.results);
          store.tvSerieList = response.data.results
        })
    }

  },

}

</script>

<template>
  <SearchBar :title="appname" @search="fetchResults" />
  <AppMain />
</template>

<style lang="scss"></style>
