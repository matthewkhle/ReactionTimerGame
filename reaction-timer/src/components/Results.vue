<template>
  <p>Reaction time = {{ score }} ms </p>
  <p class="rank">{{ rank }}</p>
</template>

<script>
export default {
    props: ['score'],
    data() {
        return {
            rank : null,
        }
    },
    updated() {
        if( this.score < 150) {
            this.rank = "fast"
        } else if (this.score < 250) {
            this.rank = "ehhh"
        } else {
            this.rank = "slow"
        }
    }
}
</script>

<style>
.rank {
    font-size: 1.4em;
    color: #0faf87;
    font-weight: bold;
  }
</style>