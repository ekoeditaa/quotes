<template>
<div>
    <div class="quotes row">
        <quote :quote="quote" v-for="quote in quotes" :key="quote">
            {{ quote }}
        </quote>
    </div>
</div>
    
</template>

<script>
import Quote from "./Quote.vue";
import { quoteBus } from "../../main";

export default {
  data: function() {
    return {
      quotes: ["Hello there", "This is second quote"]
    };
  },
  components: {
    quote: Quote
  },
  created() {
    quoteBus.$on("quoteAdded", (data) => {
      this.quotes.push(data);
    }),
      quoteBus.$on("quoteDeleted", (data) => {
        var index = this.quotes.indexOf(data);
        if (index > -1) {
          this.quotes.splice(index, 1);
        }
      });
  }
};
</script>

<style scoped>
</style>
