<script>
import DragAndDrop from '../drag-and-drop/DragAndDrop.vue';
import GlobalPlaylist from "../playlist/GlobalPlaylist.vue";
import GlobalQuote from '../quote-generator/GlobalQuote.vue';
import Tab from "./Tab.vue";
import TabsWrapper from "./TabsWrapper.vue";

export default {
  components: {
    Tab,
    TabsWrapper,
    GlobalPlaylist,
    DragAndDrop,
    GlobalQuote
  },
};
</script>

<template>
  <tabs-wrapper>
      <tab title="Intro">
          <h1>Vue Exercices</h1>
          <p>Let's practice with VueJs!</p>
      </tab>
    <tab title="Exercice 1">Create a reusable tab component.</tab>
    <tab title="Exercice 2">
      <global-playlist />
    </tab>
    <tab title="Exercice 3">
         <drag-and-drop />
    </tab>
    <tab title="Exercice 4">
      <global-quote />
    </tab>
  </tabs-wrapper>
</template>


<style scoped>
* {
  box-sizing: border-box;
}
</style>