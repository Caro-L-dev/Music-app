<script>
import QuoteHeader from './QuoteHeader.vue'
import QuoteSingle from './QuoteSingle.vue'
export default {
    name: 'App',
    components: {
        QuoteHeader,
        QuoteSingle
    },
    data() {
        return {
            quote: {
                content: 'Life is like a box of chocolates, you never know what you’re gonna run into.',
                title: 'Forrest Gump',
                author: 'Forrest'
            },
            quoteList: []
        }
    },
    methods: {
        async getQuote() {
            const data = await fetch('https://animechan.vercel.app/api/random').
            then(response => response.json());

            this.quote = {
                content: data.quote,
                title: data.anime,
                author: data.character
            };
        }
    },
    created () {
        this.getQuote();
    }
}
</script>

<template>
    <div>
        <quote-header title="Quote Generator" />
        <quote-single :quote="quote" />
    </div>
</template>

<style>
    :root {
        --primary: #D81E5D;
        --secondary: #8A4FFF;
        --tertiary: #32CBFF;
        --dark: #131A26;
        --light: #EEE;
        --grey: #848484;
    }
</style>