<template>
    <div>
        <div>
            <img 
            v-bind:src="`${currentTrack.album.images[1].url}`" 
            v-bind:alt="`${currentTrack.album.name} failed to load.`"
            style="max-width: 100%;"
            >
            <h2>Currently Playing: {{ currentTrack.name }} - by {{ currentTrack.artists[0].name }}</h2>
            <h3>{{ currentTrack.album.name }}, Track {{ currentTrack.track_number }}</h3>
        </div>
        <label for="songIDToQueue">Link for Song to Queue: </label>
        <input id="songIDToQueue" type="text">
        <Button text="Add Song" color="rgb(51, 207, 90)"/>
    </div>
  
</template>

<script>
import Button from './Button'

export default {
    name: 'CurrentlyPlaying',
    props: {
        //title: String,
        currentTrack: Object,
    },
    components: {
        Button,
    }
}
</script>

<style scoped>

    div {
        background-color: rgb(179, 190, 201);
        padding: 2em;
        margin: 2px;
    }

</style>