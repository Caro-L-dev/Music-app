<template>
    <div id="app">
      <the-header />
        <main>
           <the-player />
            <section class="playlist">
            <h3>The Playlist</h3>
            <button 
                v-for="song in songs" 
                :key="song.src" 
                @click="play(song)" 
                :class="song.src == current.src ? 'song playing' : 'song'"
                >
                {{ song.title }} ~ {{ song.artist }}
            </button>
        </section>
        </main>
    </div>
</template>

<script>
import TheHeader from './components/TheHeader.vue';
import ThePlayer from './components/ThePlayer.vue';

export default {
  components: { TheHeader, ThePlayer},
    name: "app",
    // next() {
    //     this.index++;
    //     if (this.index > this.songs.length - 1) {
    //         this.index = 0;
    //     }

    //     this.current = this.songs[this.index];
    //     this.play(this.current);
    // },
    // prev() {
    //     this.index--;
    //     if (this.index < 0) {
    //         this.index = this.songs.lenght - 1;
    //     }

    //     this.current = this.songs[this.index];
    //     this.play(this.current);
    // },
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
</style>
