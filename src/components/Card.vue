<!--
    Name: Chase Cook
    Assignment: Popular TV Shows
    Class: Web Dev II Markley
-->

<template>

<div class="card-group">
  <div class="card" v-for="i in shows" :key="i.id">
    <img class="card-img-top" v-bind:src="i.picture">
    <div class="card-body" id="cardBody">
      <h5 class="card-title" id="cardTitle"><b>{{i.title}}</b></h5>
      <p class="card-text">{{i.overview}}</p>
    </div>
  </div>
</div>

</template>

<script>
import axios from 'axios'

export default {
    name: 'Card',
    data()
    {
        return {
            // array stores info of shows
            shows: [],
            // first part of image url string
            imgUrl: 'https://image.tmdb.org/t/p/original',
            // specified number of shows, just change number of shows here
            numShows: 4
        }
    },
    mounted() {
        // axios api call
        axios.get('https://api.themoviedb.org/3/tv/popular?api_key=98f36dcb625a8af3dd49a38d649020dc&language=en-US&page=1')
        .then((response) => {
            // puts all results data into aryShows
            this.aryShows = response.data.results
            this.show(this.aryShows)
        })
    },
    methods: {
        show(aryShows) {
            // for loop through array starting by checking numShows to see how many shows are declared
            // then the desired info is pushed into the shows array above
            for (var i = 0; i < this.numShows; i++) {
                this.shows.push({
                    title: aryShows[i].name,
                    picture: this.imgUrl + aryShows[i].poster_path,
                    overview: aryShows[i].overview
                })
            }
        }
    }
}
</script>

<style scoped>
#cardBody
{
    background: honeydew;
}

#cardTitle
{
    font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
}
</style>

