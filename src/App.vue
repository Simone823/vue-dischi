<template>

  <!-- App Vue -->
  <div id="app">
    <!-- Header -->
    <header>
      <LogoHeader/>
    </header>

    <!-- Main parte centrale -->
    <main>

    </main>
    
  </div>

</template>



<script>
import LogoHeader from "./components/Logo header.vue";

export default {
  name: 'App',
  components: {
    LogoHeader,
  }
}
</script>



<style lang="scss">
// Scss impostazioni generali
@import './assets/scss/common.scss';

// Reset
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

#app {
  font-family: "Antic Slab", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  width: 100%;
  height: 100%;

  header {
    padding: 15px 20px;
    background-color: $color-blue-turquoise;
  }
}
</style>
