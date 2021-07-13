<template>

    <section>
        <div class="item">
            <img :src="`${QueuedSong.album.images[2].url}`" alt="">
        </div>

        <div class="divider"></div>

        <div class="item">
            <p>
                {{ QueuedSong.name }} by {{ QueuedSong.artists[0].name }} 
            </p>
        </div>
    </section>


    
</template>

<script>
export default {
    name: 'QueuedSong',
    props: {
        QueuedSong: {},

    }

}
</script>

<style scoped>
    .container {
        margin: 2em;
        background-color: rgb(51, 207, 90);
        opacity: 0.9;
    }
    span{
        display: block;
        padding: 7px;
        text-align: left;

        /*vertical-align:top;*/
    }
    li {
        list-style-type: none;
        display: inline;
        float: left;
        overflow: hidden;

    }
    ul {
        overflow: hidden;
    }
    img{
        vertical-align: middle;
        text-align: left;
    }
    div{
        text-align: left;
    }
    section {
        display: flex;
        flex-direction: row;
        flex: 1;
        /*margin: 0 -8px;*/
        padding: 7px;
        background-color: rgb(51, 207, 90);
        margin: 2px;
}

    section > * {
        margin: 0 8px;
}

    .tall {
        max-width: 64px;
}

    img {
        display: block;
}

    .divider {
        width: 2px;
        margin: 6px 0;
        background: rgb(0, 0, 0);
}

    .item {
        flex: 0 1 auto;
}

</style>