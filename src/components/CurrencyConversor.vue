<template>
  <div class="conversor">
    <h2>{{currencyA}} para {{currencyB}}</h2>
    <input type="text" v-model="currencyA_value" v-bind:placeholder="currencyA">
    <input type="button" value="Converter" v-on:click="conversor">
    <h2>{{currencyB_value}}</h2>
  </div>

</template>

<script>
export default {
  name: "CurrencyConversor",
  props: ['currencyA', 'currencyB'],
  data() {
    return {
      currencyA_value: '',
      currencyB_value: 0,
      }
  },
  methods: {

    async conversor() {
      const currencies = this.currencyA + '-' + this.currencyB;
      const url = `https://economia.awesomeapi.com.br/last/${currencies}`;

      const response = await fetch(url);
      const result = await response.json();
      const final = Object.values(result);

      this.currencyB_value = Number(final[0].ask).toFixed(2);
      this.currencyA_value = '';
      }
    }
};
</script>

<style scoped>
  .conversor {
    background-color: white;
    border-radius: 8px;
    padding: 20px;
    max-width: 300px;
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
  }

</style>