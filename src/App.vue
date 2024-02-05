<script>
  import AppMain from './components/AppMain.vue';

  const endpoint = 'https://41tyokboji.execute-api.eu-central-1.amazonaws.com/dev/api/v1/pokemons?per=100'
  import axios from 'axios';
  import {store} from './assets/data/store.js'

  export default {
    name: 'App',
    components: {
      AppMain
    },
    methods: {
      fetchPokemon() {
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

        console.log(res.data.limit)

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