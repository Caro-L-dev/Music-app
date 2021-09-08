<script>
import BaseBtn from './BaseBtn.vue';
export default {
    data () {
        return {
        BaseBtn,           
            current: {},
            index: 0,
            isPlaying: false,
            songs: [{
                    title: "Tokyo Revenger OST",
                    artist: "Japan artist",
                    src: require("./musics/tokyo-revengers-epic-ost.mp3"),
                },
                {
                    title: "Above",
                    artist: "Yuki Hayashi",
                    src: require("./musics/above-haikyuu-season-2-ost-vol-1-yuki-hayashi.mp3"),
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
            this.player.addEventListener('ended', function () {
                this.index++;

                if (this.index > this.songs.length - 1) {
                this.index = 0;
                }

            this.current = this.songs[this.index];
            this.play(this.current);
            }.bind(this));
            this.isPlaying = true;
        },

        pause() {
            this.player.pause();
            this.isPlaying = false;
        },

        next() {
            this.index++;
            if (this.index > this.songs.length - 1) {
                this.index = 0;
            }

            this.current = this.songs[this.index];
            this.play(this.current);
        },

        prev() {
            this.index--;
            if (this.index < 0) {
                this.index = this.songs.lenght - 1;
            }

            this.current = this.songs[this.index];
            this.play(this.current);
        },
    },

    created() {
        this.current = this.songs[this.index];
        this.player.src = this.current.src;
    }
};
</script>

<template>
    <section class="player">
        <h2 class="song-title">
            {{ current.title }} ~ <span> {{ current.artist }} </span>
        </h2>
        <div class="controls">
            <base-btn class="prev fas fa-backward" @click="prev" />
            <base-btn class="play fas fa-play" v-if="!isPlaying" @click="play"/>
            <base-btn class="pause fas fa-pause" v-else @click="pause"/>
            <base-btn class="next fas fa-forward" @click="next" />
        </div>
    </section>
</template>

<style>
    .song-title {
        color: white;
        font-size: 32px;
        font-weight: 700;
        text-transform: uppercase;
        text-align:center;
    }

    .song-title span {
        font-weight: 400;
        font-style: italic;
    }

    .controls {
        display: flex;
        justify-content: center;
        align-items: center;
        padding: 2rem 1rem;
    }

    .play, .pause, .next, .prev {
        font-weight: 700;
        padding: 0.5rem 1rem;
        margin: 0 1rem;
        color: white;
    }

    .play, .pause {
        font-size: 20px;
        border-radius: 8px;
        background-color: #CC2E5D;
    }

    .next, .prev {
        font-size: 16px;
        border-radius: 6px;
        background-color: #FF5858;
    }

    .play, .pause, .next, .prev {
        backface-visibility: hidden;
        position: relative;
        cursor: pointer;
        display: inline-block;
        white-space: nowrap;
        border-color: #7c7c7c;
        background: linear-gradient(180deg,#e6e6e6 0%,rgba(0, 0, 0, 0.25) 49%, rgba(38, 38, 38, 0.6) 51%,rgba(0, 0, 0, 0.25) 100%);
        border-radius: 5px;
    }

</style>