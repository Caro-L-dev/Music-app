<script>
import { inject } from "vue";

export default {
  name: 'Tab',
  props: ["title", "color"],
  setup() {
    const selectedTitle = inject("selectedTitle");

    return {
      selectedTitle,
    };
  },
};
</script>

<template>
  <div class="tab-content" v-show="title == selectedTitle">
    <slot />
  </div>
</template>

<style scoped>
.tab-content {
  padding: 2rem;
  border-radius: 0.5rem;
  box-shadow: 0 3px 5px 5px rgba(0, 0, 0, 0.05);
  background-image: linear-gradient(
      90deg,
      rgba(165, 165, 165, 0.03) 0%,
      rgba(165, 165, 165, 0.03) 8%,
      rgba(235, 235, 235, 0.03) 8%,
      rgba(235, 235, 235, 0.03) 9%,
      rgba(7, 7, 7, 0.03) 9%,
      rgba(7, 7, 7, 0.03) 14%,
      rgba(212, 212, 212, 0.03) 14%,
      rgba(212, 212, 212, 0.03) 17%,
      rgba(219, 219, 219, 0.03) 17%,
      rgba(219, 219, 219, 0.03) 95%,
      rgba(86, 86, 86, 0.03) 95%,
      rgba(86, 86, 86, 0.03) 100%
    ),
    linear-gradient(
      67.5deg,
      rgba(80, 80, 80, 0.03) 0%,
      rgba(80, 80, 80, 0.03) 11%,
      rgba(138, 138, 138, 0.03) 11%,
      rgba(138, 138, 138, 0.03) 17%,
      rgba(122, 122, 122, 0.03) 17%,
      rgba(122, 122, 122, 0.03) 24%,
      rgba(166, 166, 166, 0.03) 24%,
      rgba(166, 166, 166, 0.03) 27%,
      rgba(245, 245, 245, 0.03) 27%,
      rgba(245, 245, 245, 0.03) 89%,
      rgba(88, 88, 88, 0.03) 89%,
      rgba(88, 88, 88, 0.03) 100%
    ),
    linear-gradient(
      67.5deg,
      rgba(244, 244, 244, 0.03) 0%,
      rgba(244, 244, 244, 0.03) 4%,
      rgba(16, 16, 16, 0.03) 4%,
      rgba(16, 16, 16, 0.03) 10%,
      rgba(157, 157, 157, 0.03) 10%,
      rgba(157, 157, 157, 0.03) 20%,
      rgba(212, 212, 212, 0.03) 20%,
      rgba(212, 212, 212, 0.03) 83%,
      rgba(5, 5, 5, 0.03) 83%,
      rgba(5, 5, 5, 0.03) 84%,
      rgba(237, 237, 237, 0.03) 84%,
      rgba(237, 237, 237, 0.03) 100%
    ),
    linear-gradient(90deg, #ffffff, #ffffff);
}
</style>
