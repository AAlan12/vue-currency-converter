<template>
  <h1 class="text-center">Currency Converter</h1>
  <div class="line">
    <Converter coin-a="USD" coin-b="BRL"/>
    <Converter coin-a="BRL" coin-b="USD"/>
  </div>
  <div class="line">
    <Converter coin-a="CAD" coin-b="BRL"/>
    <Converter coin-a="BRL" coin-b="CAD"/>
  </div>
  <div class="line">
    <Converter coin-a="EUR" coin-b="BRL"/>
    <Converter coin-a="BRL" coin-b="EUR"/>
  </div>
  
</template>

<script>
import Converter from './components/Converter.vue';


export default {
  name: 'App',
  components: {
    Converter
}
}
</script>

<style>
#app {
  margin: auto;
  max-width: 900px;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
}
.line{
  margin-top: 40px;
  display: flex;
  justify-content: space-between;
}
.text-center{
  text-align: center;
}
</style>
