<template>
  <div class="block" v-show="show_block" @click="stopTimer">click me!</div>
</template>

<script>
export default {
    props: ['delay'],
    data() {
        return {
            show_block: false,
            timer: null,
            reactionTime: 0
        }
    },
    mounted() {
        setTimeout(() => {
            this.show_block = true
            this.startTimer()
        }, this.delay);
    },
    methods: {
        startTimer() {
            this.timer = setInterval(() => {
                this.reactionTime += 10
            }, 10)
        },
        stopTimer() {
            clearInterval(this.timer)
            console.log(this.reactionTime)
            this.$emit('end', this.reactionTime)
        },
    }
}
</script>

<style>
    .block {
        width: 400px;
        border-radius: 20px;
        background:  red;
        color: white;
        text-align: center;
        padding: 100px 0;
        margin: 40px auto;
    }
</style>