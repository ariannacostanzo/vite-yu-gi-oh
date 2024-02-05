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
  }


</style>