<script>
  import AppMain from './components/AppMain.vue';

  const endpoint = 'https://41tyokboji.execute-api.eu-central-1.amazonaws.com/dev/api/v1/pokemons?per=16'
  import axios from 'axios';
  import {store} from './assets/data/store.js'

  export default {
    name: 'App',
    components: {
      AppMain
    },
    methods: {
      fetchPokemon() {
        store.isLoading = true;
        axios.get(endpoint).then(res => {

        store.pokemons = res.data.docs.map(pokemon => {
          return {
            number: pokemon.number,
            imageUrl: pokemon.imageUrl,
            name: pokemon.name,
            type1: pokemon.type1,
            type2: pokemon.type2,
            id: pokemon._id

          }
        })
      }).then(() => {
        store.isLoading = false;
      })
      },

    },
    created() {
      this.fetchPokemon()
    }
  }
</script>

<template>
  <div class="body">
    <AppMain/>
  </div>
</template>

<style>
@import './assets/style/style.scss';
 
</style>

<!-- cose da fare:
fare un filtro per cercare i pokemon, in base al nome, al tipo, e numero;
 fare che quando clicco load more carica altri pokemon-->