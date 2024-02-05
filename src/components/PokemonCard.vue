<script>
  import {store} from '../assets/data/store.js'
  export default {
    name: ''
  }
</script>

<template>
  <div class="pokemon-card">

        <img src="../assets/images/body_bg.png" alt="">
        <div class="pokemon-info">
            <p class="pokemon-number">numero</p>
            <h3 class="pokemon-name">nome</h3>
            <span class="pokemon-type">tipo 1</span>
            <span class="pokemon-type">tipo 2</span>
        </div>
        
    </div>
  
</template>

<style lang="scss" scoped>
@use '../assets/style/colors' as *;
  .pokemon-card {
    
    flex-basis: 25%;
    padding: 1.5rem .7rem;

    img {
        max-width: 100%;
        border-radius: 10px;
    }

    .pokemon-info {
        padding: 0 1rem;

        .pokemon-number {
            color: $grey;
            text-transform: uppercase;
        }

        .pokemon-name {
            font-size: 1.5rem;
            margin-top: .4rem;
            font-weight: 500;
            margin-bottom: .5rem;
        }

        .pokemon-type {
            background-color: red;
            margin-right: 10px;
            padding: 2px 20px;
            font-size: .9rem;
            border-radius: 6px;
        }

    }

    

  }
</style>