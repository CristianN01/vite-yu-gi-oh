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
    <section>
        <div class="numbers-card">
            <h2>
                Found {{ this.cards.length }} cards!
            </h2>
        </div>
        <article >
            <div class="card" v-for="card in cards" :key="card.id">
                <img :src="card.card_images[0].image_url_small" >
                <div class="name-card">
                    {{ card.name.toUpperCase() }}
                </div>
                <div class="archetype">
                    {{ card.archetype }}
                </div>
            </div>
        </article>
    </section>

        <MainCard />
</template>

<style lang="scss" scoped>

.numbers-card {
    background-color: #212529;
    color: white;
    max-width: 1250px;
    padding: 1rem;
    
}

section {
    margin-top: 5rem;
}

article {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    max-width: 1250px;
    margin: 0 auto;
    background-color: white;
    
    .card {
        width: calc((100% / 5) - 2.5rem);
        background-color: #d48f38;
        margin-bottom: 3rem;
        

        img {
            width: 100%;
            height: auto;
            object-fit: cover;
            object-position: top;
            
        }
    }
    
    .name-card,
    .archetype {
        background-color: #d48f38;
        text-align: center;
    }

    .name-card {
        color: white;
        margin-bottom: 3rem;
    }


}

</style>