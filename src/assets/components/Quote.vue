<template>
    <div class="col-auto quote">
    <div class="" @click="removeQuote" style="width: 18rem;">
        <div class="card" style="width: 18rem;">
        <div class="card-body">
            <p class="card-text"><slot></slot></p>
        </div>
    </div>
    </div>
</div>
    
</template>

<script>
import { quoteBus } from "../../main";

export default {
    props: {
        quote: String
    },
    methods: {
        removeQuote(){
            quoteBus.$emit('quoteDeleted', this.quote);
        }
    }
};
</script>

<style scoped>
.quote {
    font-family: Arizonia;
    font-size: 30px;
    margin: 2%;
    cursor: pointer;
}
</style>
