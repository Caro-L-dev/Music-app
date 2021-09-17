<script>
import { ref, provide } from "vue";

export default {
  setup(props, { slots }) {
    const tabTitleList = ref(slots.default().map((tab) => tab.props.title));
    const selectedTitle = ref(tabTitleList.value[0]);

    provide("selectedTitle", selectedTitle);
    return {
      selectedTitle,
      tabTitleList,
    };
  },
};
</script>

<template>
  <div class="tabs">
    <ul class="tabs__header">
      <li
        v-for="title in tabTitleList"
        :key="title"
        :class="{ selected: title == selectedTitle }"
        @click="selectedTitle = title"
      >
        {{ title }}
      </li>
    </ul>
    <slot />
  </div>
</template>

<style scoped>
.tabs {
  max-width: 40rem;
  margin: 0 auto;
  margin-top: 1rem;
  font-weight: 700;
  font-size: 14px;
}

.tabs__header {
  margin-bottom: 1rem;
  list-style: none;
  padding: 0;
  display: flex;
}

.tabs__header li {
  width: 8rem;
  text-align: center;
  padding: 0.5rem 0.5rem;
  margin-right: 1rem;
  background-color: #ddd;
  border-radius: 5px;
  transition: 0.4s all ease-out;
}

.tabs__header li.selected {
  background-color: #0984e3;
  color: white;
}
</style>
