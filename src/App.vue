<template>
  <div id="app" class="grid-container" >     
    <div class="d-flex justify-content-between p-3 grid-container  grid-item">
        <div class="grid-item"></div>
        <div class="grid-item">
            <Temperatura/>
        </div>
    </div>
    <div class="d-flex justify-content-between grid-container grid-item">
        <div class="grid-item"></div>
        <div class="grid-item">
            <Notepad/>
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
