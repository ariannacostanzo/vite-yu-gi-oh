<script>
import PokemonCards from '../components/PokemonCards.vue'
import {store} from '../assets/data/store.js'
  export default {
    name: 'AppMain',
    data() {
      return {
        store,
      }
    },
    components: {
      PokemonCards
    }
  }
</script>

<template>
    <main>
      
      <div class="pokemon-container">
        <h1>Pokédex</h1>

        <div v-if="store.isLoading" id="loader-container"><i class="fa-solid fa-circle-notch fa-spin fa-4x"></i></div>

        <div v-else class="pokemon-cards-container">

          <PokemonCards/> 
          
        </div>
        <div id="load-more-container">
          <button v-if="!store.isLoading">Load more Pokémon</button>
        </div>
      </div>
      
    </main>
</template>

<style lang="scss" scoped>
@use '../assets/style/style.scss';


  main {
    background-image: url(../assets/images/container_bg.png);
    background-color: white;
    max-width: 1400px;
    margin: 0 auto;
  }

  #loader-container {
    display: flex;
    align-items: center;
    justify-content: center;  
    padding: 2rem 0;
  }

  .pokemon-container {
    margin:  auto;
    padding: 2rem;
    border-radius: 10px;
    max-width: 1100px;


    h1 {
      margin-bottom: 2rem;
    }


  }

  .pokemon-cards-container {
    display: flex;
    flex-wrap: wrap;
    background-color: #f2f2f2;
  }

  #load-more-container {

    text-align: center;
    margin: 3rem 0;

    button {
    padding: 15px 30px;
    margin: 0 auto;
    border: 0;
    border-radius: 10px;
    background-color: #30a7d7;
    color: white;
    font-size: 1.2rem;
    cursor: pointer;
  }
  }
  


</style>