<template>
    <div class="resultsBlock">
        <p>Reaction time {{ score }} ms</p>
        <p class="rank">{{ rank }}</p>
    </div>
</template>

<script>
export default {
    props: ['score'],
    data(){
        return {
            rank: null
        }
    },
    mounted() {
        if(this.score< 250){
            this.rank = "Ninja Fingers"
        }else if (this.score < 400){
            this.rank = "Rapid Fingers"
        }else{
            this.rank = "Small pace"
        }
    }
}
</script>

<style>


.rank{
    font-size: 1.4rem;
    color: black;
    font-weight: bold;
}
</style>