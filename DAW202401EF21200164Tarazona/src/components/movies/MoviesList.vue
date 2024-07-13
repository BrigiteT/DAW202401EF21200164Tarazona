
import LoginFormVue from '../auth/LoginForm.vue';
<template>
    <h5>Listado de Programas de Tv</h5>
    <div class="movies-list">
        <div class="movies-grid">
            <div class="movies-item" v-for="movies in movies" :key="movies.id">
                <moviesItem :movies="movies" />
            </div>
        </div>
    </div>
</template>

<style>
.movies-grid{
    display: grid;
    grid-template-columns: repeat(3,1fr) ;
    grid-gap: 20xp;
}

</style>

<script>
import moviesItem from 'src/components/movies/MoviesItem.vue'

export default{
    name:"moviesList",
    components: {moviesItem},
    data(){
        return {
            movies: []
        }
    },
    mounted(){
        this.loadmovies()
    },
    methods:{
        loadmovies(){
            var URL = "https://api.themoviedb.org/3/discover/tv?include_adult=false&include_null_first_air_dates=false&language=en-US&page=1&sort_by=popularity.desc"
            var token = JSON.parse(localStorage.getItem("userData")).result.token
            console.log("TOKEN es : " + token)
            console.LoginFormVue("TOKEN es : " + '')
            get(URL,{
                headers: {
                    //Authorization: 'Bearer ' + token
                    Authorization: 'Bearer eyJhbGciOiJIUzI1NiJ9.eyJhdWQiOiJjODRmMmUwODYxM2JmN2FlYTM1OGI0OTgzNDNkMWUwNiIsInN1YiI6IjVmZTUxM2M3ZTE4Yjk3MDAzYzg5NzE3MCIsInNjb3BlcyI6WyJhcGlfcmVhZCJdLCJ2ZXJzaW9uIjoxfQ.StJwmra-PsBwZTOXWg3Y06VEu8CGfAo8dXV7ZQ3RnIs'
                }
            })
            .then(response=>{
                this.movies = response.data
                console.log(JSON.stringify(response))
            }).catch(error=>{
                console.log("Ocurrio un error: " + error)
                this.$router.push("/")
            })
        }
    }
}

</script>