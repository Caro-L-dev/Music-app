<script>
export default {
    data () {
    return {
        current: {},
        songs: [{
                title: "Tokyo Revenger OST",
                artist: "Japan artist",
                src: require("../assets/musics/tokyo-revengers-epic-ost.mp3"),
            },
            {
                title: "Above - Haikyuu",
                artist: "Yuki Hayashi",
                src: require("../assets/musics/above-haikyuu-season-2-ost-vol-1-yuki-hayashi.mp3"),
            },
        ],
        player: new Audio(),
    }
    },

}
</script>

<template>
    <section class="playlist">
        <h3>The Playlist</h3>
        <base-button 
            v-for="song in songs" 
            :key="song.src" 
            @click="play(song)" 
            :class="song.src == current.src ? 'song playing' : 'song'"
            >
            {{ song.title }} ~ {{ song.artist }}
        </base-button>
    </section>
</template>

<style>
    .playlist {
        padding: 0 1rem;
    }
    
    .playlist h3 {
        color: #212121;
        font-size: 28px;
        font-weight: 400px;
        margin-bottom: 30px;
        text-align: center;
    }

    .playlist .song {
        display: block;
        width: 100%;
        padding: 1rem;
        font-size: 20px;
        font-weight: 700;
        cursor: pointer;
    }

    .playlist .song:hover {
        color: #FF5858;
    }


    .playlist .song.playing {
        color: white;
        background-image: linear-gradient(to right, #cc2e5d, #FF5858);
    }


</style>