<script>
  export default {
    name: 'SelectType',
    data() {
        return {
            pokemonTypes: [
                "Bug",
                "Dark",
                "Dragon",
                "Electric",
                "Fairy",
                "Fighting",
                "Fire",
                "Flying",
                "Ghost",
                "Grass",
                "Ground",
                "Ice",
                "Normal",
                "Poison",
                "Psychic",
                "Rock",
                "Steel",
                "Water"
            ]
        }
    }
  }
</script>

<template>
  <select>
    <option value="All">All</option>
    <option v-for="pokemonType in pokemonTypes" :value="pokemonType">{{ pokemonType }}</option>
  </select>
</template>

<style lang="scss" scoped>
  select {
    padding:  5px 15px;
  }
</style>