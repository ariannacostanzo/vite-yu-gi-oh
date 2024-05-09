<script>
  import {store} from '../assets/data/store.js'
  export default {
    name: 'PokemonCards',
    data() {
        return {
            store,
        }
    }
  }
</script>

<template>

  <div v-for="(pokemon, i) in store.pokemons" :key="pokemon.id" class="pokemon-card">
        <figure class="pokemon-img-container">
            <img :src="pokemon.imageUrl" :alt="pokemon.name" class="pokemon-img">
        </figure>
        <div class="pokemon-info">
            <p class="pokemon-number">N ° {{i+1}}</p>
            <h3 class="pokemon-name">{{ pokemon.name }}</h3>
            <span class="pokemon-type" :class="`bg${pokemon.type1}`">{{pokemon.type1}}</span>
            <span v-if="pokemon.type2" class="pokemon-type" :class="`bg${pokemon.type2}`">{{pokemon.type2}}</span>
        </div>
        
    </div>
  
</template>

<style lang="scss" scoped>
@use '../assets/style/style.scss';
@use '../assets/style/colors' as *;
  .pokemon-card {
    
    flex-basis: 25%;
    padding: 1.5rem .7rem;
    background-color: #f2f2f2;
    cursor: pointer;
    transition: .2s ease;

    &:hover {
        translate: 0 -10px;
    }

    .pokemon-img-container {
        width: 236.63px;
        height: 236.63px;
        background-color: white;
        border-radius: 10px;

    }
    .pokemon-img {
        width: 236.63px;
        height: 236.63px;
        border-radius: 10px;
        object-fit: contain;

       
    }

    .pokemon-info {
        padding: 0 1rem;

        .pokemon-number {
            color: $grey;
            text-transform: uppercase;
            font-size: .9rem;
            margin-top: .3rem;
        }

        .pokemon-name {
            font-size: 1.5rem;
            margin-top: .4rem;
            font-weight: 500;
            margin-bottom: .5rem;
        }

        .pokemon-type {
            margin-right: 10px;
            padding: 2px 20px;
            font-size: .9rem;
            border-radius: 6px;
            color: white;
        }

    }

    

  }
</style>