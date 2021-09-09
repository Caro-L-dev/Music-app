<script>
import DragAndDrop from '../drag-and-drop/DragAndDrop.vue';
import GlobalPlaylist from "../playlist/GlobalPlaylist.vue";
import Tab from "./Tab.vue";
import TabsWrapper from "./TabsWrapper.vue";

export default {
  components: {
    Tab,
    TabsWrapper,
    GlobalPlaylist,
    DragAndDrop
  },
};
</script>

<template>
  <tabs-wrapper>
      <tab title="Intro">
          <h1>Vue Exercices</h1>
          <p>Let's practice with VueJs!</p>
          <drag-and-drop />
      </tab>
    <tab title="Exercice 1">Create a reusable tab component.</tab>
    <tab title="Exercice 2">
      <global-playlist />
    </tab>
    <tab title="Exercice 3">En cours</tab>
    <tab title="Exercice 4">4</tab>
  </tabs-wrapper>
</template>
