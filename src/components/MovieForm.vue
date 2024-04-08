<script setup>
    // import { ref } from 'vue';
    // const myId = ref("item-123");
    // const imgUrl = ref("http://localhost/photo.jpg");

    function saveMovie(){
        

        // let movieForm = document.getElementById('movieForm');
        // let form_data = new FormData(movieForm);


        fetch("/api/v1/movies", {
            method: 'POST',
            // body: form_data
            
        })

            .then(function (response) {
                return response.json();
            })

            .then(function (data) {
            // display a success message
                console.log(data);
            })

            .catch(function (error) {
                console.log(error);
            });
    }
</script>


<template>
    <form id="movieForm" class="form-group mb-3" @submit.prevent="saveMovie" enctype="multipart/form-data">
        <div>
            <label for="title" class="form-label">Movie Title:</label>
            <input type="text" name="title" class="form-control">
        </div>

        <div>
            <label for="description" class="form-label">Movie Description:</label>
            <textarea name="description" class="form-control"></textarea>
        </div>

        <div>
            <label for="poster" class="form-label">Movie Poster:</label>
            <input type="file" name="poster" class="form-control" accept=".jpg,.png,.jpeg">
        </div>

        <button type="submit">Save Movie</button>
    </form>
</template>


<style>
/* Add any component specific styles here */
</style>