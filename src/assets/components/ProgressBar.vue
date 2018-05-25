<template>
    <div class="full-bar"> 
        <div v-if="noOfQuotes > 0" class="bar" :style="getWidth">{{ noOfQuotes }} / 10 </div>
    </div>
</template>

<script>
import { quoteBus } from "../../main";

export default {
    data: () => {
        return {
            noOfQuotes: 2,
        };
    },
    computed: {
        getWidth() {
            return 'width: ' + String(this.noOfQuotes * 10) + '%';
        }
    },
    created() {
        quoteBus.$on('quoteAdded', (data) => {
            this.noOfQuotes++;
        }),
        quoteBus.$on('quoteDeleted', (data) => {
            this.noOfQuotes--;
        })
    }
    
}
</script>

<style scoped>
.full-bar {
    margin: 0;
    width: 100%;
    height: 30px;
    background-color:#EEE;
    border: 10px;
    border-radius: 5px;
}
.bar {
    background-color: teal;
    height: 30px;
    border-radius: 5px;
    text-align: center;
    font-size: 20px;
    color: #EEE;
}
</style>
