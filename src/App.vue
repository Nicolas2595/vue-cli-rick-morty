<template>

  <div id="app">
   <Header />
   <main>
        <CharactersList />
   </main>
  </div>
  
</template>

<script>

import Header from '../src/components/Header';
import CharactersList from '../src/components/CharactersList';


export default {
  name: 'App',
  components: {
    Header,
    CharactersList
  }
}

</script>

<style lang="scss">

@import '~bootstrap/scss/bootstrap';

@import "~@fontsource/roboto/index.css";
@import "~@fontsource/roboto/700.css";

body {
  font-family: 'Roboto', sans-serif;
}

main {
  background-color: #22b4cf;
}

</style>
