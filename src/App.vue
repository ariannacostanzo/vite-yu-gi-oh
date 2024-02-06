<script>
  import AppMain from './components/AppMain.vue';
  import MainHeader from './components/MainHeader.vue';
  const baseEndpoint = 'https://41tyokboji.execute-api.eu-central-1.amazonaws.com/dev/api/v1/pokemons?per=8'
  const basePokemonTypes = 'https://41tyokboji.execute-api.eu-central-1.amazonaws.com/dev/api/v1/pokemons/types1'
  import axios from 'axios';
  import {store} from './assets/data/store.js'

  export default {
    name: 'App',
    components: {
      AppMain, MainHeader
    },
    methods: {
      //faccio una chiamata api e filtro le chiavi da prendere
      fetchPokemon(endpoint) {
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

          store.pagination = res.data
          // console.log(store.pagination)

        }).then(() => {
          store.isLoading = false;
        })
        
        },
        //in base al tipo che mi arriva filtro i pokemon
      fetchPokemonType(pokemonType) {
        const endpointType = `${baseEndpoint}&eq[type1]=${pokemonType}`
        if (pokemonType === 'All') {
          this.fetchPokemon(baseEndpoint)
        } else {
          this.fetchPokemon(endpointType)

        }
      },
      //ottengo dall'api i tipi di pokemon
      fetchTypes() {
        axios.get(basePokemonTypes).then(res => {
          store.pokemonTypes = res.data
          // console.log(store.pokemonTypes)
        })
      },
      loadMorePokemon() {
        console.log('funziona')
      }
    },
    created() {
      this.fetchPokemon(baseEndpoint)
      this.fetchTypes()
    }
  }
</script>

<template>
  <div class="body">
    <AppMain @type-selected="fetchPokemonType" @load-button-clicked="loadMorePokemon"/>
  </div>
</template>

<style>
@import './assets/style/style.scss';
 
</style>

<!-- cose da fare:
fare un filtro per cercare i pokemon, in base al nome, al tipo, e numero;
 fare che quando clicco load more carica altri pokemon, usare la paginazione, pagina attuale e successiva-->