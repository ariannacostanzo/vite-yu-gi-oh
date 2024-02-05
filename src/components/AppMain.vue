<script>
import PokemonCard from '../components/PokemonCard.vue'
  export default {
    name: 'AppMain',
    data() {
      return {
      }
    },
    components: {
      PokemonCard
    }
  }
</script>

<template>
    <main>
      

      <div class="pokemon-container">

        <h1>Pokédex</h1>

        <div class="pokemon-cards-container">

          <PokemonCard/>
          
        </div>

      </div>
      

    </main>
</template>

<style lang="scss" scoped>
@use '../assets/style/style.scss';


  main {
    background-image: url(../assets/images/container_bg.png);
    background-color: white;
    max-width: 1300px;
    margin: 0 auto;
  }


  .pokemon-container {
    background-color: white;
    margin:  auto;
    padding: 2rem;
    border-radius: 10px;
    max-width: 1000px;


    h1 {
      margin-bottom: 2rem;
    }


  }

  .pokemon-cards-container {
    display: flex;
    flex-wrap: wrap;
  }


</style>