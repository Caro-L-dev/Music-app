<script>
import QuoteHeader from "./QuoteHeader.vue";
import QuoteList from "./QuoteList.vue";
import QuoteSingle from "./QuoteSingle.vue";
export default {
  name: "App",
  components: {
    QuoteHeader,
    QuoteSingle,
    QuoteList,
  },
  data() {
    return {
      quote: {},
      quoteList: [],
    };
  },
  methods: {
    async getQuote() {
      if (this.quote.content) {
        this.quoteList = [...this.quoteList, this.quote];
      }

      const data = await fetch(
        "https://animechan.vercel.app/api/random"
      ).then((response) => response.json());

      this.quote = {
        content: data.quote,
        title: data.anime,
        author: data.character,
      };
    },
  },
  created() {
    // this.getQuote();
  },
};
</script>

<template>
  <div>
    <quote-header title="Quote Generator" />
    <quote-single :quote="quote" />
    <div class="quote-btn__wrapper">
      <button @click="getQuote">
        Generate
      </button>
    </div>
    <quote-list :quoteList="quoteList" />
  </div>
</template>

<style scoped>
.quote-btn__wrapper {
  display: flex;
  justify-content: center;
  padding: 0rem 2rem;
  margin: 3rem auto;
}

button {
  border: none;
  outline: none;
  background-color: #0984e3;
  padding: 0.5rem 1rem;
  border-radius: 1rem;
  color: white;
  font-size: 16px;
  font-weight: 700;
  text-transform: uppercase;
  cursor: pointer;
  transition: 0.4s;
}
</style>
