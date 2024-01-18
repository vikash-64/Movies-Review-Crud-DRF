<template>
    <div class="w3-container ">
        <form class="w3-container w3-card-4 w3-light-grey" @submit.prevent="createPost">
            <h2>Add Movies</h2>

            <p><label>Movie Name</label>
                <input class="w3-input w3-border" name="first" type="text" v-model="formData.name">
            </p>

            <p><label>Last Name</label>
                <input class="w3-input w3-border" name="last" type="date" v-model="formData.release_date">
            </p>
            <p>
                <button class="w3-btn w3-light-green">Add Movie</button>
            </p>
        </form>
    </div>
</template>

<script>
import axios from 'axios';
export default {
    data() {
        return {
            formData: {

                name: '',
                release_date: '',
            }
        }
    },

    methods: {
        createPost(){

            axios.post('http://127.0.0.1:8000/api/movies/' , this.formData).then((response)=>{
                console.log(response)
            }).catch((error)=>{
                console.log(error)
            })

        }
    },

}
</script>

<style  scoped></style>