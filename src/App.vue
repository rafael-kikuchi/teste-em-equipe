<template>
  <v-app>
    <v-main>
      <BuscarPais/>
    </v-main>
  </v-app>
</template>

<script>
  import BuscarPais from './components/BuscarPais'
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