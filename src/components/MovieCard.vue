<script>
    export default{
        props:['movieView'],
    }
</script>

<template>
    <main class="container">
        <div class="card">
            <img :src="movieView.Poster" alt="Poster">
            <div class="cardInfo">
                <h4>{{movieView.Title}}</h4>
                <p>Year: {{ movieView.Year }}</p>
            </div>
        </div>
    </main>
    
</template>

<style>
@import url('https://fonts.googleapis.com/css2?family=Roboto&display=swap');

    .card{
        width: 200px;
        height: 350px;
        margin: 10px;
        border-radius: 5px;
        box-shadow: 2px 2px 7px grey;
        overflow: hidden;
        background: white;
    }
    .card img{
        width: 200px;
        height: 250px;
        object-fit: cover;
    }
    .cardInfo{
        font-family: 'Roboto', sans-serif;
        padding: 10px;
    }
    .cardInfo h4{
        font-size: 13px;
        margin: 0px;
    }
    .cardInfo p{
        font-size: 10px;
    }
</style> 