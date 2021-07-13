<template>
  <div id="app">
    <div class="jumbotron">
      <Codificador/>

      <p>Respuestas: 1: B  /  2: B  /  3: C  /  4: B  /  5: A</p>
    </div>
  </div>
</template>

<script>
import Codificador from './components/Codificador.vue';

export default {
  name: 'App',
  components: {
    Codificador
  }
}
</script>

<style>
  h1 {
    color: blue;
  }

  .jumbotron {
    padding: 32px !important;
  }
</style>
