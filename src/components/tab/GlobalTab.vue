<script>
import DragAndDrop from "../drag-and-drop/DragAndDrop.vue";
import TheHeader from "../header/TheHeader.vue";
import GlobalPlaylist from "../playlist/GlobalPlaylist.vue";
import GlobalQuote from "../quote-generator/GlobalQuote.vue";
import GlobalWeather from "../weather-app/GlobalWeather.vue";
import GlobalGame from "../game/GlobalGame.vue";
import Tab from "./Tab.vue";
import TabsWrapper from "./TabsWrapper.vue";


export default {
  components: {
    Tab,
    TabsWrapper,
    GlobalPlaylist,
    DragAndDrop,
    GlobalQuote,
    TheHeader,
    GlobalWeather,
    GlobalGame
  },
};
</script>

<template>
  <tabs-wrapper>
    <tab title="Intro">
      <the-header />
    </tab>
    <tab title="Music Player">
      <global-playlist />
    </tab>
    <tab title="Drag and Drop">
      <drag-and-drop />
    </tab>
    <tab title="Quotes">
      <global-quote />
    </tab>
    <tab title="Weather App">
      <global-weather />
    </tab>
    <tab title="Game">
      <global-game />
    </tab>
  </tabs-wrapper>
</template>
