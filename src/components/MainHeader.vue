<script>
  import SelectType from './SelectType.vue';
  export default {
    name: 'MainHeader',
    components: {
        SelectType
    },
    emits: ['selected-type'],
    methods: {
        funzione(pokemonType) {
        console.log('funziona:' + pokemonType)
      }
    }
  }
</script>

<template>
    <div>
        <h1>Pokédex</h1>
        <SelectType @type-selected="funzione" />
    </div>
</template>

<style lang="scss" scoped>

    div {
        display: flex;
        align-items: flex-start;
        justify-content: space-between;
    }
  
    h1 {
        margin-bottom: 2rem;
    }
</style>