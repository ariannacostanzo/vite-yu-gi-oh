<script>
import {store} from '../assets/data/store.js'
  export default {
    name: 'AppMain',
    data() {
      return {
        store,
      }
    }
  }
</script>

<template>
    <main>
      

      <div class="pokemon-container">

        <h1>Pokédex</h1>

        <div class="pokemon-cards-container">
          
          <!-- da spostare -->
          <div class="pokemon-card">
            <img src="../assets/images/body_bg.png" alt="">
            <p>numero</p>
            <p>nome</p>
            <span>tipo 1</span>
            <span>tipo 2</span>
          </div>
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

  // da spostare


</style>