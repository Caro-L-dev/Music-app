<script>
export default {
    data () {
        return {
            current: {},
            index: 0,
            isPlaying: false,
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
    methods: {
        play(song) {
            if (typeof song.src != "undefined") {
                this.current = song;
                this.player.src = this.current.src;
            }

            this.player.play();
            this.isPlaying = true;
        },

        pause() {
        this.player.pause();
        this.isPlaying = false;
        },
    },
        created() {
        this.current = this.songs[this.index];
        this.player.src = this.current.src;
       // this.player.play();
    },
}
</script>

<template>
    <section class="player">
        <h2 class="song-title">
            {{ current.title }} ~ <span> {{ current.artist }} </span>
        </h2>
        <div class="control">
            <button class="prev" @click="prev">Prev</button>
            <button class="play" v-if="!isPlaying" @click="play">Play</button>
            <button class="pause" v-else @click="pause">Pause</button>
            <button class="next" @click="next">Next</button>
        </div>
    </section>
</template>