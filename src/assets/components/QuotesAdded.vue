<template>
<div class="header">
    <h2 class="top"> Quotes Added </h2>
    <progress-bar></progress-bar>
</div>

    
</template>

<script>
import ProgressBar from "./ProgressBar.vue";

export default {
    components: {
        progressBar: ProgressBar
    }
}
</script>

<style scoped>
.header {
    margin: 5%;
}
.top {
    font-family: 'Courier New', Courier, monospace;
}

</style>
