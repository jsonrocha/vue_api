<template>
    <div>
        <h2>Trending Movies</h2>
        <div class="body">
            <div v-for="movie in movies" :key="movie.id">
                <div class="moviebox">
                    <div>
                        <div>
                            <h5>{{movie.title}}</h5>
                        </div>
                    </div>
                    <img 
                    :src="getImageURL(movie.poster_path)" 
                    :alt="movie.title" >
                    <div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
  name: "movies",
  props: {
    movies: Array
  },
  methods: {
    getImageURL: function(imagePath) {
      return "https://image.tmdb.org/t/p/w200" + imagePath;
    }
  }
};
</script>

<style>
.moviebox {
    margin: 30px;
    cursor: pointer;
}

h2 {
    text-align: center;
    margin-bottom: 3px;
}

h5 {
    text-align: center;
    max-width: 210px;
    margin-bottom: 10px;
}

.body {
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    justify-content: center;
}

img {
  border-radius: 5px;
}
</style>