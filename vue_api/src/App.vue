<template>
  <div id="app">
    <Search v-on:process-user-input="updateSearchTerm"/>
    <Movies :movies="movies"/>
  </div>
</template>

<script>
import Search from "./components/Search.vue";
import Movies from "./components/Movies.vue";
export default {
  name: "app",
  components: {
    Search,
    Movies
  },
  data: function() {
    return {
      movies: [],
      searchTerm: ""
    };
  },
  mounted: function() {
    let URL = `https://api.themoviedb.org/3/trending/movie/day?api_key=e68c1a67b9b6a0fff17d9ed980ca72cf
`;
    fetch(URL)
      .then(resp => resp.json())
      .then(movieData => {
        this.movies = movieData.results;
      });
  },
  methods: {
    updateSearchTerm: function(userInput) {
      this.searchTerm = userInput;
    }
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  background-color: azure;
  color:darkslategray;
}

body {
  margin: 0px;
}
</style>