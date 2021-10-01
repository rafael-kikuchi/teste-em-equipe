<template>
  <div id="app">
    <BuscarPais/>
  </div>
</template>

<script>
import BuscarPais from './components/BuscarPais.vue'

export default {
  name: 'App',
  components: {
    BuscarPais
  }
}
</script>

<style>
  *{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }
</style>
