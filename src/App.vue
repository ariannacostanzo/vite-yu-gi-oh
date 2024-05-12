<script>
  import AppMain from './components/AppMain.vue';
  import MainHeader from './components/MainHeader.vue';
  let baseEndpoint = `https://41tyokboji.execute-api.eu-central-1.amazonaws.com/dev/api/v1/pokemons?per=`
  const basePokemonTypes = 'https://41tyokboji.execute-api.eu-central-1.amazonaws.com/dev/api/v1/pokemons/types1'
  import axios from 'axios';
  import {store} from './assets/data/store.js'

  export default {
    name: 'App',
    components: {
      AppMain, MainHeader
    },
    data() {
      return {
        perPage: 16,
        scrollPosition: 0,
        currentPage: 1,
        currentEndpoint: null,
        firstType: '',
        secondType: '',
        initialEndpoint: baseEndpoint
      }
    },
    computed: {
      pagePosition() {
        return window.scrollY
      },
      getEndpoint() {
        return this.initialEndpoint + this.perPage
      }
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

          this.scrollPosition = window.scrollY
          window.scrollTo(0, this.scrollPosition)
        }).catch(err => { }).then(() => {
            setTimeout(() => {
              store.isLoading = false
            }, 500)
          })
        
        },
        filterPokemonType(options) {
          this.currentPage = 1
          const object = options;
          const type = object.type;
          const typeSelected = object.optionSelected
          // let endpoint = `${baseEndpoint}${this.perPage}`
          if (type === 'firstType') {
            if (typeSelected !== 'All') {
              this.firstType =  `&eq[type1]=${typeSelected}`
            } else {
              this.firstType = ''
            }
          }
          if (type === 'secondType') {
            if (typeSelected !== 'All') {
              this.secondType = `&eq[type2]=${typeSelected}`
            } else {
              this.secondType = ''
            }
          }
          
          this.currentEndpoint = this.getEndpoint + this.firstType + this.secondType
          this.fetchPokemon(this.currentEndpoint)
        },
        //ottengo dall'api i tipi di pokemon
        fetchTypes() {
          axios.get(basePokemonTypes).then(res => {
            store.pokemonTypes = res.data
          }).catch(err => {console.log(err)}).then()

        },

        //quando clicco aggiungo tot pokemon in più
        loadMorePokemon() {
          this.currentPage++
          let page = `&page=${this.currentPage}`
          
          axios.get(`${ this.currentEndpoint }${page}`).then(res => {
            store.isLoading = true;
            const newPokemon = res.data.docs.map(pokemon => {

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
            newPokemon.forEach(pokemon => {
              store.pokemons.push(pokemon)
            })
          }).catch(err => { }).then(() => {
            setTimeout(() => {
              store.isLoading = false
            }, 500)
          })
        },

      // createEndpoint(per, type) {
      //   if (type) {
      //     baseEndpoint = `https://41tyokboji.execute-api.eu-central-1.amazonaws.com/dev/api/v1/pokemons?per=${per}&eq[type1]=${type}`
      //   } else {
      //     baseEndpoint = `https://41tyokboji.execute-api.eu-central-1.amazonaws.com/dev/api/v1/pokemons?per=${perPage}`
      //   }

      //   return baseEndpoint
      // }

    },
    created() {

      this.currentEndpoint = `${baseEndpoint}${this.perPage}`
      this.fetchPokemon(this.currentEndpoint)
      this.fetchTypes()
      
    },
    
  }
</script>

<template>
  <div class="body">
    <AppMain @type-selected="filterPokemonType" @load-button-clicked="loadMorePokemon"/>
    <span id="anchor"></span>
  </div>
</template>

<style>
@import './assets/style/style.scss';
 
</style>

<!-- cose da fare:
fare un filtro per cercare i pokemon, in base al nome, al tipo, e numero;
 fare che quando clicco load more carica altri pokemon, usare la paginazione, pagina attuale e successiva
da sistemare il load more-->
 

<!-- sistemare il button load more quando premo un altro tipo  -->