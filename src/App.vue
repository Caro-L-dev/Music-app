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
  created () {
    this.current = this.songs[this.index];
    this.player.src = this.current.src;
  }
};
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