<script>
import PokemonCards from '../components/PokemonCards.vue';
import LoadingButton from '../components/LoadingButton.vue';
import LoadingBall from '../components/LoadingBall.vue';
import {store} from '../assets/data/store.js'
  export default {
    name: 'AppMain',
    data() {
      return {
        store,
      }
    },
    components: {
      PokemonCards, LoadingButton, LoadingBall
    },
    methods: {
      nextPage() {
        console.log('prossima pagina')
       
      }
    }
  }
</script>

<template>
    <main>
      
      <div class="pokemon-container">
        <h1>Pokédex</h1>

        <LoadingBall v-if="store.isLoading" />

        <div v-else class="pokemon-cards-container">
          <PokemonCards/> 
        </div>

        <LoadingButton v-if="!store.isLoading" @click="nextPage"/>
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

  // #loader-container {
  //   display: flex;
  //   align-items: center;
  //   justify-content: center;  
  //   padding: 2rem 0;
  //   font-size: 1.4rem;
  //   font-weight: bold;

  //   .loading-ball {
  //     width: 100px;
  //     margin-left: 20px;
  //   }
  // }

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

  


</style>