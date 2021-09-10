<script>
import QuoteHeader from './QuoteHeader.vue'
import QuoteSingle from './QuoteSingle.vue'
export default {
    name: 'App',
    components: {QuoteHeader, QuoteSingle}
}
</script>

<template>
    <div>
        <quote-header title="Quote Generator" />
        <quote-single />
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