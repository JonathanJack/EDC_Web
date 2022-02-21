<template>
  <div id="app" >     
   <Temperatura/>
  <!-- <Cripto prop-coin='BTC'/> -->
  <!-- <Notepad/> -->
   
  </div>
</template>

<script>


import Temperatura from './components/Temperatura.vue'
  //  import Cripto from './components/Cripto.vue'
  // import Notepad from './components/Notepad.vue'

export default {
  name: 'App',
  components: {
    // Notepad
    Temperatura
    // Cripto
  },  
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;          
}
</style>
