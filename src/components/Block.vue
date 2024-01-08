<template>
    <div @click="stopTimer" v-if="showBlock" class="block">
      click me
    </div>
</template>

<script>
export default {
    props: ['delay'],
    data(){
        return {
            showBlock: false,
            timer: null,
            reactionTime: 0
        }
    },
    mounted() {
        console.log("mounted")
        setTimeout(() => {
            this.showBlock = true;
            this.startTimer();
            console.log(this.delay)
        }, this.delay)
    },
    methods: {
        startTimer(){
            this.timer = setInterval(()=> {
                this.reactionTime += 10
            }, 10)
        },
        stopTimer(){
            clearInterval(this.timer)
            this.$emit('end', this.reactionTime)
        }
    }
}
</script>

<style>
.block{
    width: 400px;
    border-radius: 26px;
    background: rgb(223, 223, 17);
    color: white;
    text-align: center;
    padding: 100px 0;
    margin: 40px auto;
}
</style>