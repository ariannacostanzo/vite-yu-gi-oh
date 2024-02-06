<script>
  import SelectType from './SelectType.vue';
  export default {
    name: 'MainHeader',
    components: {
        SelectType
    },
    emits: ['type-selected']
    
  }
</script>

<template>
    <div>
        <h1>Pokédex</h1>
        <SelectType @type-selected="$emit('type-selected', $event)" />
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