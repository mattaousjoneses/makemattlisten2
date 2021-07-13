<template>
  <div class="container">    
    <CurrentlyPlaying :currentTrack="currentTrack"/>
  </div>
  <br>
  <div :key="queuedSong.id" v-for="queuedSong in QueuedSongList">
    <QueuedSong :QueuedSong='queuedSong'/>
  </div>
</template>

<script>

import CurrentlyPlaying from './components/CurrentlyPlaying'
import QueuedSong from './components/QueuedSong'


export default {
  name: 'App',
  components: {
    CurrentlyPlaying,
    QueuedSong
  },
  methods: {
    async changeCurrentTrack(){
      //const res = await fetch('https://api.spotify.com/v1/tracks/5kRiMfPdtzVpuh3zj7ja6i?si=14005a6c4f204b25&access_token=BQBfJ_nw-ImBcgWIh_l-aiJ9JBgMhlycNCYj9tLiwje8DVg0CKA8FKiqxPBxMrFBoBw5DFSsaH5ibexmaefJXfVGJv192CmXBvc4KYbyCd-PhP_a48hmOaTTXW-FrgayMbbyRuLNNerXofEPrZlVx0UxkZoV414Aln4')
      //const {results} = await res.json()

    const results = await fetch(
        'https://api.spotify.com/v1/tracks/'+
        '5kRiMfPdtzVpuh3zj7ja6i?si=14005a6c4f204b25'+
        '&access_token='+
        'BQBDb_fS6WNsullK-hR5JLmLRdZMFEAfJcSJCZduutjqbGHdnszqLf8rhaV0rS4KvNa9Kt3x6KOywBHwN3ruaxnP2psf1PHYUMSVgd68s6DLGBvrshSuLpXuP84Z8Z2dvmWUc4Xzi3gOP7wvrp5DhqohBSCTtfWxl6w'
        )
        .then(response => response.json())
      //.then(data => console.log(data))

        this.currentTrack.album = results.album
        this.currentTrack.artists = results.artists
        this.currentTrack.duration_ms = results.duration_ms
        this.currentTrack.explicit = results.explicit
        this.currentTrack.external_ids = results.external_ids
        this.currentTrack.href = results.href
        this.currentTrack.id = results.id
            //is_playable: true,
        this.currentTrack.name = results.name
        this.currentTrack.track_number = results.track_number
        this.currentTrack.type = results.type
        this.currentTrack.uri = results.uri
    }
  },
  data() {
    return {
      currentTrack: {
    "album": {
        "album_type": "single",
        "artists": [
            {
                "external_urls": {
                    "spotify": "https://open.spotify.com/artist/716NhGYqD1jl2wI1Qkgq36"
                },
                "href": "https://api.spotify.com/v1/artists/716NhGYqD1jl2wI1Qkgq36",
                "id": "716NhGYqD1jl2wI1Qkgq36",
                "name": "Bizarrap",
                "type": "artist",
                "uri": "spotify:artist:716NhGYqD1jl2wI1Qkgq36"
            },
            {
                "external_urls": {
                    "spotify": "https://open.spotify.com/artist/3p3jPcp8b7WL9XYj4xlsWj"
                },
                "href": "https://api.spotify.com/v1/artists/3p3jPcp8b7WL9XYj4xlsWj",
                "id": "3p3jPcp8b7WL9XYj4xlsWj",
                "name": "Snow Tha Product",
                "type": "artist",
                "uri": "spotify:artist:3p3jPcp8b7WL9XYj4xlsWj"
            }
        ],
        
        "external_urls": {
            "spotify": "https://open.spotify.com/album/3GN1tT5enSZQ6lMDtls3an"
        },
        "href": "https://api.spotify.com/v1/albums/3GN1tT5enSZQ6lMDtls3an",
        "id": "3GN1tT5enSZQ6lMDtls3an",
        "images": [
            {
                "height": 640,
                "url": "https://i.scdn.co/image/ab67616d0000b2730427a473bc9cec1a1df4d14b",
                "width": 640
            },
            {
                "height": 300,
                "url": "https://i.scdn.co/image/ab67616d00001e020427a473bc9cec1a1df4d14b",
                "width": 300
            },
            {
                "height": 64,
                "url": "https://i.scdn.co/image/ab67616d000048510427a473bc9cec1a1df4d14b",
                "width": 64
            }
        ],
        "name": "Snow Tha Product: Bzrp Music Sessions, Vol. 39",
        "release_date": "2021-04-28",
        "release_date_precision": "day",
        "total_tracks": 1,
        "type": "album",
        "uri": "spotify:album:3GN1tT5enSZQ6lMDtls3an"
    },
    "artists": [
        {
            "external_urls": {
                "spotify": "https://open.spotify.com/artist/716NhGYqD1jl2wI1Qkgq36"
            },
            "href": "https://api.spotify.com/v1/artists/716NhGYqD1jl2wI1Qkgq36",
            "id": "716NhGYqD1jl2wI1Qkgq36",
            "name": "Bizarrap",
            "type": "artist",
            "uri": "spotify:artist:716NhGYqD1jl2wI1Qkgq36"
        },
        {
            "external_urls": {
                "spotify": "https://open.spotify.com/artist/3p3jPcp8b7WL9XYj4xlsWj"
            },
            "href": "https://api.spotify.com/v1/artists/3p3jPcp8b7WL9XYj4xlsWj",
            "id": "3p3jPcp8b7WL9XYj4xlsWj",
            "name": "Snow Tha Product",
            "type": "artist",
            "uri": "spotify:artist:3p3jPcp8b7WL9XYj4xlsWj"
        }
    ],
    
    "disc_number": 1,
    "duration_ms": 177442,
    "explicit": true,
    "external_ids": {
        "isrc": "UYB282101015"
    },
    "external_urls": {
        "spotify": "https://open.spotify.com/track/3ke6it1vTmHtz2ApcIVUz5"
    },
    "href": "https://api.spotify.com/v1/tracks/3ke6it1vTmHtz2ApcIVUz5",
    "id": "3ke6it1vTmHtz2ApcIVUz5",
    "is_local": false,
    "name": "Snow Tha Product: Bzrp Music Sessions, Vol. 39",
    "popularity": 81,
    "preview_url": "https://p.scdn.co/mp3-preview/505dce4e3d5090d196b6b5e5250dc8c849ca3c24?cid=adaaf209fb064dfab873a71817029e0d",
    "track_number": 1,
    "type": "track",
    "uri": "spotify:track:3ke6it1vTmHtz2ApcIVUz5"
},
      QueuedSongList: [
        {
    "album": {
        "album_type": "album",
        "artists": [
            {
                "external_urls": {
                    "spotify": "https://open.spotify.com/artist/3SEJQy90Vgg1aSnZ9b4AU9"
                },
                "href": "https://api.spotify.com/v1/artists/3SEJQy90Vgg1aSnZ9b4AU9",
                "id": "3SEJQy90Vgg1aSnZ9b4AU9",
                "name": "Krizz Kaliko",
                "type": "artist",
                "uri": "spotify:artist:3SEJQy90Vgg1aSnZ9b4AU9"
            }
        ],
        
        "external_urls": {
            "spotify": "https://open.spotify.com/album/34XTf0Xzu8MUdBOAwiqjzg"
        },
        "href": "https://api.spotify.com/v1/albums/34XTf0Xzu8MUdBOAwiqjzg",
        "id": "34XTf0Xzu8MUdBOAwiqjzg",
        "images": [
            {
                "height": 640,
                "url": "https://i.scdn.co/image/ab67616d0000b273de4db8be000802ffdb8d97fe",
                "width": 640
            },
            {
                "height": 300,
                "url": "https://i.scdn.co/image/ab67616d00001e02de4db8be000802ffdb8d97fe",
                "width": 300
            },
            {
                "height": 64,
                "url": "https://i.scdn.co/image/ab67616d00004851de4db8be000802ffdb8d97fe",
                "width": 64
            }
        ],
        "name": "NEH'MIND",
        "release_date": "2012-11-27",
        "release_date_precision": "day",
        "total_tracks": 7,
        "type": "album",
        "uri": "spotify:album:34XTf0Xzu8MUdBOAwiqjzg"
    },
    "artists": [
        {
            "external_urls": {
                "spotify": "https://open.spotify.com/artist/3SEJQy90Vgg1aSnZ9b4AU9"
            },
            "href": "https://api.spotify.com/v1/artists/3SEJQy90Vgg1aSnZ9b4AU9",
            "id": "3SEJQy90Vgg1aSnZ9b4AU9",
            "name": "Krizz Kaliko",
            "type": "artist",
            "uri": "spotify:artist:3SEJQy90Vgg1aSnZ9b4AU9"
        },
        {
            "external_urls": {
                "spotify": "https://open.spotify.com/artist/3p3jPcp8b7WL9XYj4xlsWj"
            },
            "href": "https://api.spotify.com/v1/artists/3p3jPcp8b7WL9XYj4xlsWj",
            "id": "3p3jPcp8b7WL9XYj4xlsWj",
            "name": "Snow Tha Product",
            "type": "artist",
            "uri": "spotify:artist:3p3jPcp8b7WL9XYj4xlsWj"
        }
    ],
    
    "disc_number": 1,
    "duration_ms": 168715,
    "explicit": true,
    "external_ids": {
        "isrc": "USA2P1274461"
    },
    "external_urls": {
        "spotify": "https://open.spotify.com/track/5KheomZdjhk0uZK39zJpJq"
    },
    "href": "https://api.spotify.com/v1/tracks/5KheomZdjhk0uZK39zJpJq",
    "id": "5KheomZdjhk0uZK39zJpJq",
    "is_local": false,
    "name": "Damage (feat. Snow Tha Product)",
    "popularity": 39,
    "preview_url": "https://p.scdn.co/mp3-preview/313bff9dbcd25478ad30e1c9690924b2fd22673b?cid=adaaf209fb064dfab873a71817029e0d",
    "track_number": 2,
    "type": "track",
    "uri": "spotify:track:5KheomZdjhk0uZK39zJpJq"
},
    {
    "album": {
        "album_type": "album",
        "artists": [
            {
                "external_urls": {
                    "spotify": "https://open.spotify.com/artist/5BIOo2mCAokFcLHXO2Llb4"
                },
                "href": "https://api.spotify.com/v1/artists/5BIOo2mCAokFcLHXO2Llb4",
                "id": "5BIOo2mCAokFcLHXO2Llb4",
                "name": "Kublai Khan TX",
                "type": "artist",
                "uri": "spotify:artist:5BIOo2mCAokFcLHXO2Llb4"
            }
        ],
        "external_urls": {
            "spotify": "https://open.spotify.com/album/4XOJCBjxUbqrbSJkBrjlDu"
        },
        "href": "https://api.spotify.com/v1/albums/4XOJCBjxUbqrbSJkBrjlDu",
        "id": "4XOJCBjxUbqrbSJkBrjlDu",
        "images": [
            {
                "height": 640,
                "url": "https://i.scdn.co/image/ab67616d0000b27374ef44a0fead86c42b87dc61",
                "width": 640
            },
            {
                "height": 300,
                "url": "https://i.scdn.co/image/ab67616d00001e0274ef44a0fead86c42b87dc61",
                "width": 300
            },
            {
                "height": 64,
                "url": "https://i.scdn.co/image/ab67616d0000485174ef44a0fead86c42b87dc61",
                "width": 64
            }
        ],
        "name": "Nomad",
        "release_date": "2017-09-29",
        "release_date_precision": "day",
        "total_tracks": 10,
        "type": "album",
        "uri": "spotify:album:4XOJCBjxUbqrbSJkBrjlDu"
    },
    "artists": [
        {
            "external_urls": {
                "spotify": "https://open.spotify.com/artist/5BIOo2mCAokFcLHXO2Llb4"
            },
            "href": "https://api.spotify.com/v1/artists/5BIOo2mCAokFcLHXO2Llb4",
            "id": "5BIOo2mCAokFcLHXO2Llb4",
            "name": "Kublai Khan TX",
            "type": "artist",
            "uri": "spotify:artist:5BIOo2mCAokFcLHXO2Llb4"
        }
    ],
    
    "disc_number": 1,
    "duration_ms": 177258,
    "explicit": true,
    "external_ids": {
        "isrc": "QMRSZ1702093"
    },
    "external_urls": {
        "spotify": "https://open.spotify.com/track/7bBtjbVD7P0h3rnFvmmySB"
    },
    "href": "https://api.spotify.com/v1/tracks/7bBtjbVD7P0h3rnFvmmySB",
    "id": "7bBtjbVD7P0h3rnFvmmySB",
    "is_local": false,
    "name": "B.C.",
    "popularity": 32,
    "preview_url": "https://p.scdn.co/mp3-preview/279340a5627d3d3597f377bdc48cc0d98a687ef2?cid=adaaf209fb064dfab873a71817029e0d",
    "track_number": 7,
    "type": "track",
    "uri": "spotify:track:7bBtjbVD7P0h3rnFvmmySB"
}
      ],
    }
    
  },
  created() {
    this.changeCurrentTrack()
  },

  
}
</script>

<style >
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;

}
body{
    background-color: rgb(55, 62, 70);

}

</style>
