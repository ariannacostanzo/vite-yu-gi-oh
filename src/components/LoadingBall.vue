<script>
  export default {
    name: 'LoadingBall'
  }
</script>

<template>
  <div id="loader-container">Loading...<img src="../assets/images/favicon.png" alt="pokeball" class="loading-ball"></div>
</template>

<style lang="scss" scoped>
  #loader-container {
    display: flex;
    align-items: center;
    justify-content: center;  
    padding: 2rem 0;
    font-size: 1.4rem;
    font-weight: bold;

    .loading-ball {
      width: 100px;
      margin-left: 20px;
    }
  }
</style>