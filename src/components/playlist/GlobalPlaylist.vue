<script>
import ThePlayer from './ThePlayer.vue';
import ThePlaylist from './ThePlaylist.vue';

export default {
    components: {
        ThePlayer,
        ThePlaylist
    }
};
</script>

<template>
    <div>
        <div class="device__wrapper">
            <the-player />
            <the-playlist />
        </div>
    </div>
</template>

<style>
.device__wrapper {
    background-color: rgb(158, 158, 158);
    border-radius: 1rem;
    width: 100%;
    max-width: 20rem;
    margin: 0 auto;
    padding: 2rem;
    border: inset 5px rgb(214, 40, 9);
    background-image: linear-gradient(45deg, rgb(240, 99, 99) 0%, rgb(240, 99, 99) 11%,rgb(230, 115, 107) 11%, rgb(230, 115, 107) 24%,rgb(220, 132, 114) 24%, rgb(220, 132, 114) 29%,rgb(210, 148, 122) 29%, rgb(210, 148, 122) 45%,rgb(199, 164, 129) 45%, rgb(199, 164, 129) 87%,rgb(189, 181, 137) 87%, rgb(189, 181, 137) 90%,rgb(179, 197, 144) 90%, rgb(179, 197, 144) 100%),linear-gradient(67.5deg, rgb(240, 99, 99) 0%, rgb(240, 99, 99) 11%,rgb(230, 115, 107) 11%, rgb(230, 115, 107) 24%,rgb(220, 132, 114) 24%, rgb(220, 132, 114) 29%,rgb(210, 148, 122) 29%, rgb(210, 148, 122) 45%,rgb(199, 164, 129) 45%, rgb(199, 164, 129) 87%,rgb(189, 181, 137) 87%, rgb(189, 181, 137) 90%,rgb(179, 197, 144) 90%, rgb(179, 197, 144) 100%),linear-gradient(135deg, rgb(240, 99, 99) 0%, rgb(240, 99, 99) 11%,rgb(230, 115, 107) 11%, rgb(230, 115, 107) 24%,rgb(220, 132, 114) 24%, rgb(220, 132, 114) 29%,rgb(210, 148, 122) 29%, rgb(210, 148, 122) 45%,rgb(199, 164, 129) 45%, rgb(199, 164, 129) 87%,rgb(189, 181, 137) 87%, rgb(189, 181, 137) 90%,rgb(179, 197, 144) 90%, rgb(179, 197, 144) 100%),linear-gradient(90deg, rgb(156, 174, 7),rgb(129, 53, 44));
    background-blend-mode:overlay,overlay,overlay,normal;
}
</style>
