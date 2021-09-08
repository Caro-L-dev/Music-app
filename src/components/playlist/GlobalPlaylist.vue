<script>
import TheHeader from './TheHeader.vue';
import ThePlayer from './ThePlayer.vue';
import ThePlaylist from './ThePlaylist.vue';

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
        <div class="color">
            <the-header />
            <the-player />
            <the-playlist />
        </div>
    </div>
</template>

<style>
.color {
    background-color: rgb(158, 158, 158);
    border-radius: 1rem;
    width: 100%;
    max-width: 20rem;
    margin: 0 auto;
    padding: 2rem;
    border-top: rgb(255, 176, 85) 6px solid;
    border-right: white 4px inset;
    border-left: 5px solid blueviolet;
}
</style>
