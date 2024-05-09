<script>
  import {store} from '../assets/data/store.js'
  export default {
    name: 'SelectType',
    data() {
        return {
            optionSelected: 'All'
        }
    },
    emits: ['option-selected'],
    props: {
      options: Array,
      defaultLabel: String,
      type: String
    }
  }
</script>

<template>
  <select @change="$emit('option-selected', {optionSelected, type})" v-model="optionSelected">
    <option :value="defaultLabel">{{ defaultLabel }}</option>
    <option v-for="(option, i) in options" :key="i" :value="option">{{ option }}</option>
  </select>
</template>

<style lang="scss" scoped>
  select {
    padding:  5px 15px;
  }
</style>