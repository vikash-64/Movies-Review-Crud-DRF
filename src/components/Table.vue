<template>
    <div class="w3-container " >
        <div class="w3-container w3-card-4 w3-light-grey k">
            <h2>Movies List</h2>
            <table class="w3-table-all w3-hoverable  t ">
            <thead>
                <tr class="w3-light-grey">
                    <th>Movie Name</th>
                    <th>Release Date</th>

                </tr>
            </thead>
            <tr v-for="(movie, index) in movies" :key="index">
                <td>{{ movie.name }}</td>
                <td>{{ movie.release_date }}</td>

            </tr>
        </table>
        </div>
        


    </div>
</template>

<script>
import axios from 'axios';
export default {
    data() {
        return {
            movies: []

        }
    },

    mounted() {
        this.getMovieDetails();
    },

    methods: {
        getMovieDetails() {

            axios.get('http://127.0.0.1:8000/api/movies/').then((response) =>
               
                this.movies = response.data   

            ).catch((error)=>{
                console.log(error)
            })

        }
    },
}
</script>

<style  scoped>
.k{
    margin-top: 10px;
}

.t{
    margin-bottom: 15px;
}
</style>