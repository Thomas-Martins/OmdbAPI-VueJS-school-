<script >
  import axios from "axios"
  import MovieCard from "./components/MovieCard.vue"
  export default{
    components:{
        MovieCard
    },
    data(){
      return{
        movies: [],
        input:""
      }
    },
    methods:{
      loadMovies(){
        const key = "c5f26518";
        const input = this.input.trim();
        axios.get(`http://www.omdbapi.com/?s=${input}&apikey=${key}`).then((response) => {
          this.movies = response.data.Search
        })
      },
    },
  }
</script>

<template>
    <div class="searchBar">
        <input type="text" placeholder="Nom du film" v-model="input" @keydown.enter="loadMovies">
        <button @click="loadMovies">Recherchez</button>
    </div>
  <div class="content">
    <MovieCard v-for="movie in movies" :movieView="movie" />
  </div>
  

</template>

<style>

.searchBar{
    text-align: center;
}
.content{
    display: grid;
    grid-template-columns: repeat(4, 1fr);
}
</style>