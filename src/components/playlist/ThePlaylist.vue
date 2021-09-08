<script>
export default {
    data () {
    return {
        current: {},
        songs: [{
                title: "Tokyo Revenger OST",
                artist: "Japan artist",
                src: require("./musics/tokyo-revengers-epic-ost.mp3"),
            },
            {
                title: "Above - Haikyuu",
                artist: "Yuki Hayashi",
                src: require("./musics/above-haikyuu-season-2-ost-vol-1-yuki-hayashi.mp3"),
            },
        ],
        player: new Audio(),
    }
    },

}
</script>

<template>
    <section class="playlist">
        <p>Choose your song:</p>
        <base-btn 
            v-for="song in songs" 
            :key="song.src" 
            @click="play(song)" 
            :class="song.src == current.src ? 'playlist__song-playing' : 'playlist__song'"
            >
            {{ song.title }} ~ {{ song.artist }}
        </base-btn>
        <span class="fas fa-angle-down" />
    </section>
</template>

<style>
    .playlist {
        overflow: hidden;
        text-align: center;
        background-color: rgb(51, 51, 51);
        border-radius: 1rem;
        border: inset 5px #FEA606;
        color: white;
        font-weight: 700;
        cursor: pointer;
    }
    
    .playlist__title {
        font-size: 24px;
        margin-bottom: 1rem;
    }

    .playlist__song {
        display: block;
        width: 100%;
        padding: 0.5rem;
        font-size: 14px;

    }

    .playlist__song:hover {
        background-color: rgb(0, 0, 0);
        color: #f98315;
    }

    .playlist__song-playing {
        color: white;
        background-image: linear-gradient(to right, #cc2e5d, #FF5858);
    }

    .fa-angle-down {
        padding: 1rem;
    }
</style>