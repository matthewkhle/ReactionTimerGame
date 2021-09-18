<template>
  <div class="block" v-show="show_block">click me!</div>
</template>

<script>
export default {
    props: ['delay'],
    data() {
        return {
            show_block: false,
        }
    },
    mounted() {
        setTimeout(() => {
            this.show_block = true
        }, this.delay);
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