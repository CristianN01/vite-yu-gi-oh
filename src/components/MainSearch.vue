<script>
import axios from 'axios';

export default {
  data() {
    return {
      typeCard: [],
    }
  },
  methods: {
    selectType(){
        axios.get('https://db.ygoprodeck.com/api/v7/archetypes.php')
        .then( (response) => {
            // handle success
            console.log(response.data);
            this.typeCard = response.data;
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
        this.selectType();
  }
}

</script>

<template>
    <div class="dropdown">
        <button class="dropbtn">selectType</button>
        <div class="dropdown-content">
            <a v-for="type in typeCard" :key="type.archetype_name" @click="$emit('clickType')"> {{ type.archetype_name }}</a>
        </div>
    </div>
</template>

<style lang="scss" scoped>

.dropbtn {
  background-color: #212529;
  color: white;
  padding: 16px;
  font-size: 16px;
  border: none;
  cursor: pointer;
  position: absolute;
  left: 5.95rem;
  top: 2.1rem;
}

.dropdown {
  position: relative;
  display: inline-block;
}

.dropdown-content {
  display: none;
  position: absolute;
  background-color: #f9f9f9;
  min-width: 160px;
  box-shadow: 0px 8px 16px 0px rgba(0,0,0,0.2);
  z-index: 1;
  top: 5.4rem;
  left: 5.95rem;
}

.dropdown-content a {
  color: black;
  padding: 12px 16px;
  text-decoration: none;
  display: block;
}

.dropdown-content a:hover {background-color: #f1f1f1}

.dropdown:hover .dropdown-content {
  display: block;
}

.dropdown:hover .dropbtn {
  background-color: #212529c4;
}

</style>