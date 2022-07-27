<template>
  <h2>Currency Converter</h2>
  <div class="box">
    <Currency-Conversor currency-a="USD" currency-b="BRL"/>
    <Currency-Conversor currency-a="BRL" currency-b="USD"/>
  </div>
  <div class="box">
    <Currency-Conversor currency-a="EUR" currency-b="BRL"/>
    <Currency-Conversor currency-a="BRL" currency-b="EUR"/>
  </div>
</template>

<script>
import CurrencyConversor from './components/CurrencyConversor.vue'

export default {
  name: 'App',
  components: {
    CurrencyConversor,
  }
}
</script>

<style>
#app {
  background-color: #f4f4f4;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 8px;
}

.box {
  display: flex;
  justify-content: space-around;
  margin-top: 32px;
}
</style>
