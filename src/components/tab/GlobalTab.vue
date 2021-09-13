<script>
import DragAndDrop from "../drag-and-drop/DragAndDrop.vue";
import TheHeader from "../header/TheHeader.vue";
import GlobalPlaylist from "../playlist/GlobalPlaylist.vue";
import GlobalQuote from "../quote-generator/GlobalQuote.vue";
import GlobalWeather from '../weather-app/GlobalWeather.vue';
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
  },
};
</script>

<template>
  <tabs-wrapper>
    <tab title="Intro">
      <the-header />
    </tab>
    <tab title="Exercice 1">
      <global-playlist />
    </tab>
    <tab title="Exercice 2">
      <drag-and-drop />
    </tab>
    <tab title="Exercice 3">
      <global-quote />
    </tab>
    <tab title="Exercice 4">
      <global-weather />
    </tab>
  </tabs-wrapper>
</template>
