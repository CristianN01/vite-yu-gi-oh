<script>
import MainSearch from './MainSearch.vue'
import MainCardsList from './MainCardsList.vue'
import axios from 'axios';


export default {
    components: {
        MainSearch,
        MainCardsList,
    },
  data() {
    return {
        cards: [],
            
    }
  },
  methods: {
    getCards(){
        axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=30&offset=0')
        .then( (response) => {
            // handle success
            console.log(response.data.data);
            this.cards = response.data.data;
        })
        .catch(function (error) {
            // handle error
            console.log(error);
        })
        .finally(function () {
            // always executed
        });
    }
  },
  created(){
        this.getCards();
  }
}
</script>

<template>
        <!-- <MainSearch /> -->
        
        <MainCardsList :cards="cards"/>
</template>

<style lang="scss" scoped>
@use '../styles/general.scss'

</style>