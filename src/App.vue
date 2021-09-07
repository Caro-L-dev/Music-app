<template>
  <div id="app">
    <header>
      <h1>My Music</h1>
    </header>
    <main>
      <section class="player">
        <h2 class="song-title">
          {{ current.title }} -
          <span>
            {{ current.artist }}
            </span>
          </h2>
          <div class="control">
            <button class="prev">Prev</button>
            <button class="play" v-if="!isPlaying" @click="play">Play</button>
            <button class="pause" v-else @click="pause">Pause</button>
            <button class="next">Next</button>
          </div>
      </section>
    </main>
  </div>
</template>

<script>
export default {
  name: "app",
  data () {
    return {
      current: {},
      index: 0,
      songs: [
        {
          title: 'Tokyo Revenger OST',
          artist: '...',
          src: require('./assets/tokyo-revengers-epic-ost.mp3')
        },
        {
        title: 'Above - Haikyuu',
        artist: 'Yuki Hayashi',
        src: require('./assets/above-haikyuu-season-2-ost-vol-1-yuki-hayashi.mp3')
        }
      ],
      player: new Audio()
    }
  },
  methods: {
    play (song) {
      if (typeof song.src != "undefined") {
        this.current = song;
        this.player.src = this.current.src;
      }
  
      this.player.play();
      this.isPlaying = true;
      }
    },
    pause () {
      this.player.pause();
      this.isPlaying = false;
    },

  created () {
    this.current = this.songs[this.index];
    this.player.src = this.current.src;
  }
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
body {
  font-family: sans-serif;
}
header {
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 15px;
  background-color: black;
  color: white;
}
</style>