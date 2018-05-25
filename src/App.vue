<template>
    <div class="container">
        <quotesAdded></quotesAdded>
        <addQuote></addQuote>
        <quotes></quotes>
        <info></info>
    </div>
</template>

<script>
import ProgressBar from "./assets/components/ProgressBar.vue";
import AddQuote from "./assets/components/AddQuote.vue";
import Quote from "./assets/components/Quote.vue";
import Quotes from "./assets/components/Quotes.vue";
import QuotesAdded from "./assets/components/QuotesAdded.vue";
import info from "./assets/components/Info.vue";

    export default {
        components: {
            addQuote: AddQuote,
            progressBar: ProgressBar,
            quote: Quote,
            quotes: Quotes,
            quotesAdded: QuotesAdded,
            info
        }        
    }
</script>

<style>
</style>
