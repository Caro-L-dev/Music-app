<script>
import TheHeader from './components/TheHeader.vue';
import ThePlayer from './components/ThePlayer.vue';
import ThePlaylist from './components/ThePlaylist.vue';
import BasebuttonDocs from './docs/BasebuttonDocs';

export default {
    components: {
        TheHeader,
        ThePlayer,
        ThePlaylist,
        BasebuttonDocs
    }
};
</script>

<template>
    <div class="wrapper">
        <the-header />
        <main>
            <the-player />
            <the-playlist />
        </main>
        <basebutton-docs />
    </div>
</template>

<style>
.wrapper {
    background-color: rgb(192, 192, 192);
}

main {
    width: 100%;
    max-width: 30rem;
    margin: 0 auto;
    padding: 2rem;
}
</style>
