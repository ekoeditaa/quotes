<template>
<form class="add-quote">
<div class="form-group">
    <label> Quote </label>
    <textarea class="form-control" id="typedQuote"></textarea>
</div>
<div class="text-center"><button class="btn btn-primary mx-auto" @click.prevent="addQuote()"> Add Quote </button></div>
</form>
    
</template>

<script>
import { quoteBus } from "../../main";

export default {
  data: function() {
    return {
      quote: "",
      noOfQuotes: 2
    };
  },
  methods: {
    addQuote() {
      this.quote = document.getElementById("typedQuote").value;
      if (this.quote != "" && this.noOfQuotes < 10) {
        this.noOfQuotes++;
        quoteBus.$emit("quoteAdded", this.quote);
        document.getElementById("typedQuote").value = "";
      } else if (this.noOfQuotes == 10) {
        alert("Too many quotes! Delete some first");
      } else {
        alert("Please type a proper quote!");
      }
      console.log(this.noOfQuotes);
    }
  },
  created() {
    quoteBus.$on("quoteDeleted", data => {
      this.noOfQuotes--;
    });
  }
};
</script>

<style scoped>
.add-quote {
  margin: auto;
  width: 50%;
}
.add-quote label {
  font-size: 20px;
  font-family: "Courier New", Courier, monospace;
}
</style>
