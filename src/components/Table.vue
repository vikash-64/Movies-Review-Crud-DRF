<template>
    <div class="w3-container">
        <h2>Movies List</h2>

        <table class="w3-table-all w3-hoverable">
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

            axios.get(`http://127.0.0.1:8000/api/movies/`).then((response) =>
               
                this.movies = response.data   

            ).catch((error)=>{
                console.log(error)
            })

        }
    },
}
</script>

<style  scoped></style>