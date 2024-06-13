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
        axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=1000&offset=0')
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
    },
    archetype(archetypeCard){
        axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=1000&archetype=archetypeCard')
        .then( (response) => {
            // handle success
            // console.log(response.data.data);
            this.cards = response.archetypeCard;
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
        <MainSearch @clickType="archetype" />
        <MainCardsList :cards="cards"/>
</template>

<style lang="scss" scoped>
@use '../styles/general.scss'

</style>