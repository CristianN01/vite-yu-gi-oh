<script>
export default {
  data() {
    return {
      
    }
  }
}
</script>

<template>
    <section class="header">
        <img src="https://upload.wikimedia.org/wikipedia/commons/2/21/Yu-Gi-Oh%21.png" >
            <h1>Yu-Gi-Oh Api</h1>
    </section>
</template>


<style lang="scss" scoped>
@use '../styles/general.scss';

    .header {
        display: flex;
        justify-content: start;
        margin: 0;
        background-color: white;
        padding: 1rem 0;


        img {
            width: 10%;
            margin: 0;
        }

        h1 {
            margin: 0;
            align-self: center;
        }
    }
</style>