<script>
import TheHeader from './components/TheHeader.vue';
import ThePlayer from './components/ThePlayer.vue';
import ThePlaylist from './components/ThePlaylist.vue';

export default {
    components: {
        TheHeader,
        ThePlayer,
        ThePlaylist
    }
};
</script>

<template>
    <div>
        <the-header />
        <main>
            <the-player />
            <the-playlist />
        </main>
    </div>
</template>

<style>
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: sans-serif;
}

main {
    width: 100%;
    max-width: 30rem;
    margin: 0 auto;
    padding: 2rem;
}
</style>
