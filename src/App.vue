<script>
// import GlobalPlaylist from './components/playlist/GlobalPlaylist';
import GlobalTabVue from './components/tab/GlobalTab.vue';

export default {
    components: {
        // GlobalPlaylist,
        GlobalTabVue
    }
};
</script>

<template>
<h1>Vue Exercices</h1>
<p>Let's practice with VueJs!</p>
    <!-- <div class="playlist__bg">
        <global-playlist />
    </div> -->
    <global-tab-vue />
</template>

<style scoped>
 .playlist__bg {
    padding: 1rem;
    max-width: 30rem;
    margin: 0 auto; 
    background-image: linear-gradient(344deg, rgb(197, 160, 165) 0%, rgb(197, 160, 165) 20%,rgb(206, 134, 161) 20%, rgb(206, 134, 161) 38%,rgb(215, 108, 156) 38%, rgb(215, 108, 156) 68%,rgb(225, 82, 152) 68%, rgb(225, 82, 152) 78%,rgb(234, 55, 148) 78%, rgb(234, 55, 148) 80%,rgb(243, 29, 143) 80%, rgb(243, 29, 143) 96%,rgb(252, 3, 139) 96%, rgb(252, 3, 139) 100%),linear-gradient(208deg, rgb(197, 160, 165) 0%, rgb(197, 160, 165) 20%,rgb(206, 134, 161) 20%, rgb(206, 134, 161) 38%,rgb(215, 108, 156) 38%, rgb(215, 108, 156) 68%,rgb(225, 82, 152) 68%, rgb(225, 82, 152) 78%,rgb(234, 55, 148) 78%, rgb(234, 55, 148) 80%,rgb(243, 29, 143) 80%, rgb(243, 29, 143) 96%,rgb(252, 3, 139) 96%, rgb(252, 3, 139) 100%),linear-gradient(189deg, rgb(197, 160, 165) 0%, rgb(197, 160, 165) 20%,rgb(206, 134, 161) 20%, rgb(206, 134, 161) 38%,rgb(215, 108, 156) 38%, rgb(215, 108, 156) 68%,rgb(225, 82, 152) 68%, rgb(225, 82, 152) 78%,rgb(234, 55, 148) 78%, rgb(234, 55, 148) 80%,rgb(243, 29, 143) 80%, rgb(243, 29, 143) 96%,rgb(252, 3, 139) 96%, rgb(252, 3, 139) 100%),linear-gradient(230deg, rgb(197, 160, 165) 0%, rgb(197, 160, 165) 20%,rgb(206, 134, 161) 20%, rgb(206, 134, 161) 38%,rgb(215, 108, 156) 38%, rgb(215, 108, 156) 68%,rgb(225, 82, 152) 68%, rgb(225, 82, 152) 78%,rgb(234, 55, 148) 78%, rgb(234, 55, 148) 80%,rgb(243, 29, 143) 80%, rgb(243, 29, 143) 96%,rgb(252, 3, 139) 96%, rgb(252, 3, 139) 100%),linear-gradient(69deg, rgb(197, 160, 165) 0%, rgb(197, 160, 165) 20%,rgb(206, 134, 161) 20%, rgb(206, 134, 161) 38%,rgb(215, 108, 156) 38%, rgb(215, 108, 156) 68%,rgb(225, 82, 152) 68%, rgb(225, 82, 152) 78%,rgb(234, 55, 148) 78%, rgb(234, 55, 148) 80%,rgb(243, 29, 143) 80%, rgb(243, 29, 143) 96%,rgb(252, 3, 139) 96%, rgb(252, 3, 139) 100%),linear-gradient(90deg, rgb(77, 249, 52),rgb(153, 163, 31));
    background-blend-mode:overlay,overlay,overlay,overlay,overlay,normal;
 }
</style>