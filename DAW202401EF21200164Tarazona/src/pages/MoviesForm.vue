<template>
    <div class="movies-page">
      <div class="movies-filter q-ml-md q-mr-xl">
        <moviesFilter />
      </div>
      <div class="movies-list q-mr-md">
        <moviesList />
      </div>
    </div>
  </template>
  <style>
  .movies-page {
    display: flex;
    justify-content: space-between;
  }
  
  .movies-filter {
    width: 25%;
  }
  
  .movies-list {
    width: 75%;
  }
  </style>
  <script>
  
  import moviesFilter from 'src/components/movies/moviesFilter.vue'
  import moviesList from 'src/components/movies/moviesList.vue';
  
  export default {
    name: "moviesPage",
    components: {
      moviesFilter,
      moviesList
    }
  }
  
  </script>