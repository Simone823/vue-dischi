<template>

  <!-- App Vue -->
  <div id="app">
    <!-- Header -->
    <header>
      <LogoHeader/>
      <SelectOption @filtra="recuperoValue"/>
    </header>

    <!-- Main parte centrale -->
    <main>
      <DiscWrapper
        :valueRecuperatoDaApp="valueRecuperato"
      />
    </main>
    
  </div>

</template>



<script>
import LogoHeader from "./components/LogoHeader.vue";
import DiscWrapper from "./components/DiscWrapper.vue";
import SelectOption from "./components/SelectOption.vue"

export default {
  name: 'App',
  components: {
    LogoHeader,
    DiscWrapper,
    SelectOption,
  },

  data() {
    return {
      // Recupero valueSelect da SelectOption
      valueRecuperato: "",
    }
  },

  methods: {
    // Recupero valueSelect
    recuperoValue: function (valueSelect) {
        this.valueRecuperato = valueSelect;
        console.log(this.valueRecuperato);
    },
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
  height: 100vh;
  display: flex;
  flex-direction: column;

  header {
    padding: 15px 20px;
    background-color: $color-blue-turquoise;
    display: flex;
    align-items: center;
    gap: 20px;
  }

  main {
    background-color: $color-blue-turquoise-dark;
    flex-grow: 1;
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 30px 0;
  }
}
</style>
