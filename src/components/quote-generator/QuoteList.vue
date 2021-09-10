<script>
export default {
  props: ["quoteList"],
};
</script>

<template>
  <section class="quote-list">
    <div
      class="quote-list__single-quote"
      v-for="(quote, quoteIndex) in quoteList.slice().reverse()"
      :key="quoteIndex"
    >
      <div class="quote-list__content">
        {{ quote.content }}
      </div>
    </div>
  </section>
</template>

<style scoped>
.quote-list {
  padding: 2rem;
  max-width: 72rem;
  margin: 0 auto;
}

.quote-list__single-quote {
  background-color: #dddddd;
  padding: 1rem;
  border-radius: 1rem;
  margin-bottom: 1rem;
}

.quote-list__content {
  overflow: hidden;
  text-overflow: ellipsis;
  white-space: nowrap;
  line-height: 1rem;
  max-height: 1.2rem;
}

.quote-list__content:hover {
  white-space: unset;
  max-height: unset;
}
</style>
