<script>
import PokemonCards from '../components/PokemonCards.vue'
  export default {
    name: 'AppMain',
    data() {
      return {
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

        

        <div class="pokemon-cards-container">

          <PokemonCards/> 
          
        </div>
        <div id="load-container">
          <button>Load more Pokémon</button>
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

  #load-container {

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