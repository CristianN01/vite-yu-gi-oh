<script>
import MainCard from './MainCard.vue'

export default {
    components: {
        MainCard,
    },
  data() {
    return {
      
    }
  },
  props: {
    cards: {
        type: Array,
        required: true
    }
  }
}
</script>

<template>
    <h1>
        Number of Cards : {{ cards.length }}
    </h1>
        <MainCard />
</template>

<style>

</style>