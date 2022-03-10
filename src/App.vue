<template>

  <!-- App Vue -->
  <div id="app">
    <!-- Header -->
    <header>
      <LogoHeader/>
    </header>

    <!-- Main parte centrale -->
    <main>
      <DiscWrapper/>
    </main>
    
  </div>

</template>



<script>
import LogoHeader from "./components/Logo header.vue";
import DiscWrapper from "./components/DiscWrapper.vue";

export default {
  name: 'App',
  components: {
    LogoHeader,
    DiscWrapper,
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
  width: 100vw;
  height: 100vh;
  display: flex;
  flex-direction: column;

  header {
    padding: 15px 20px;
    background-color: $color-blue-turquoise;
  }

  main {
    background-color: $color-blue-turquoise-dark;
    flex-grow: 1;
    display: flex;
    align-items: center;
    justify-content: center;
  }
}
</style>
