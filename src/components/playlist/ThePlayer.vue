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
        <div class="player__screen">
            <h2 class="player__song-title">
                {{ current.title }} 
                <br>
                ~ 
                <br>
                <span> {{ current.artist }} </span>
            </h2>
        </div>
        <div class="player__controls">
            <base-btn class="prev fas fa-backward" @click="prev" />
            <base-btn class="play fas fa-play" v-if="!isPlaying" @click="play"/>
            <base-btn class="pause fas fa-pause" v-else @click="pause"/>
            <base-btn class="next fas fa-forward" @click="next" />
        </div>
    </section>
</template>

<style>
    .player__screen {
        display: flex;
        justify-content: center;
        align-items: center;
        padding: 1em;
        color: white;
        border-radius: 1rem;
        background: rgb(28,50,31);
        border: inset 5px #FEA606;
        background-image: linear-gradient(231deg, rgba(233, 233, 233, 0.01) 0%, rgba(233, 233, 233, 0.01) 25%,rgba(10, 10, 10, 0.01) 25%, rgba(10, 10, 10, 0.01) 50%,rgba(237, 237, 237, 0.01) 50%, rgba(237, 237, 237, 0.01) 75%,rgba(200, 200, 200, 0.01) 75%, rgba(200, 200, 200, 0.01) 100%),linear-gradient(344deg, rgba(2, 2, 2, 0.03) 0%, rgba(2, 2, 2, 0.03) 20%,rgba(10, 10, 10, 0.03) 20%, rgba(10, 10, 10, 0.03) 40%,rgba(100, 100, 100, 0.03) 40%, rgba(100, 100, 100, 0.03) 60%,rgba(60, 60, 60, 0.03) 60%, rgba(60, 60, 60, 0.03) 80%,rgba(135, 135, 135, 0.03) 80%, rgba(135, 135, 135, 0.03) 100%),linear-gradient(148deg, rgba(150, 150, 150, 0.03) 0%, rgba(150, 150, 150, 0.03) 14.286%,rgba(15, 15, 15, 0.03) 14.286%, rgba(15, 15, 15, 0.03) 28.572%,rgba(74, 74, 74, 0.03) 28.572%, rgba(74, 74, 74, 0.03) 42.858%,rgba(175, 175, 175, 0.03) 42.858%, rgba(175, 175, 175, 0.03) 57.144%,rgba(16, 16, 16, 0.03) 57.144%, rgba(16, 16, 16, 0.03) 71.42999999999999%,rgba(83, 83, 83, 0.03) 71.43%, rgba(83, 83, 83, 0.03) 85.71600000000001%,rgba(249, 249, 249, 0.03) 85.716%, rgba(249, 249, 249, 0.03) 100.002%),linear-gradient(122deg, rgba(150, 150, 150, 0.01) 0%, rgba(150, 150, 150, 0.01) 20%,rgba(252, 252, 252, 0.01) 20%, rgba(252, 252, 252, 0.01) 40%,rgba(226, 226, 226, 0.01) 40%, rgba(226, 226, 226, 0.01) 60%,rgba(49, 49, 49, 0.01) 60%, rgba(49, 49, 49, 0.01) 80%,rgba(94, 94, 94, 0.01) 80%, rgba(94, 94, 94, 0.01) 100%),linear-gradient(295deg, rgba(207, 207, 207, 0.02) 0%, rgba(207, 207, 207, 0.02) 25%,rgba(47, 47, 47, 0.02) 25%, rgba(47, 47, 47, 0.02) 50%,rgba(142, 142, 142, 0.02) 50%, rgba(142, 142, 142, 0.02) 75%,rgba(76, 76, 76, 0.02) 75%, rgba(76, 76, 76, 0.02) 100%),linear-gradient(73deg, rgba(81, 81, 81, 0.03) 0%, rgba(81, 81, 81, 0.03) 12.5%,rgba(158, 158, 158, 0.03) 12.5%, rgba(158, 158, 158, 0.03) 25%,rgba(136, 136, 136, 0.03) 25%, rgba(136, 136, 136, 0.03) 37.5%,rgba(209, 209, 209, 0.03) 37.5%, rgba(209, 209, 209, 0.03) 50%,rgba(152, 152, 152, 0.03) 50%, rgba(152, 152, 152, 0.03) 62.5%,rgba(97, 97, 97, 0.03) 62.5%, rgba(97, 97, 97, 0.03) 75%,rgba(167, 167, 167, 0.03) 75%, rgba(167, 167, 167, 0.03) 87.5%,rgba(22, 22, 22, 0.03) 87.5%, rgba(22, 22, 22, 0.03) 100%),linear-gradient(90deg, hsl(137,0%,23%),hsl(137,0%,23%));
    }
    .player__song-title {
        color: white;
        font-size: 24px;
        font-weight: 700;
        text-transform: uppercase;
        text-align:center;
    }

    .player__song-title span {
        font-weight: 400;
        font-size: 16px;
        font-style: italic;
    }

    .player__controls {
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
        font-size: 24px;
    }

    .next, .prev {
        font-size: 14px;
    }

    .play, .pause, .next, .prev {
        backface-visibility: hidden;
        position: relative;
        cursor: pointer;
        display: inline-block;
        white-space: nowrap;
        border-color: #7c7c7c;
        background: linear-gradient(180deg,#fffd7a 0%,rgba(187, 0, 0, 0.25) 49%, rgba(233, 0, 0, 0.6) 51%,rgba(255, 0, 0, 0.25) 100%);
        border-radius: 5px;
        box-shadow: rgba(17, 17, 26, 0.1) 0px 1px 0px;
    }

</style>