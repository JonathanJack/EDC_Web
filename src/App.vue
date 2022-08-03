<template>
  <div id="app" class="grid-container p-4"  style="height: 100vh">     
    <div class="d-flex  grid-container  grid-item" style="height: 50vh">
        <div class="grid-item w-100"></div>
        <div class="grid-item w-100 d-flex justify-content-end">
            <Temperatura/>
        </div>
    </div>
    <div class="d-flex justify-content-between grid-container grid-item" >
        <div class="grid-item w-100"></div>
        <div class="grid-item w-100 d-flex justify-content-end">
            <Notepad style="height: 25vh;"/>
        </div>
    </div>
    <!-- <Mirror/> -->
  <!-- <Cripto prop-coin='BTC'/> -->
   
  </div>
</template>

<script>


import Temperatura from './components/Temperatura.vue'
  //  import Cripto from './components/Cripto.vue'
  import Notepad from './components/Notepad.vue'
  // import Mirror from './components/Mirror.vue'


export default {
  name: 'App',
  components: {
    Notepad,
    Temperatura,
    // Mirror
    // Cripto
  },  
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;          
}
</style>
