<template>
  <div>
    <h1>Avocoin</h1>
    <h2>1 BTC &rarr; {{ price }}🥑</h2>
  </div>
</template>

<script>
const axios = require('axios')

export default {
  name: 'PriceAvocado',
  data () {
    return {
      price: 0
    }
  },
  created() {
    axios.get('https://avocoinapp.herokuapp.com/')
    .then(response => {
      this.price = response.data.price
    })
  }
}
</script>

<style lang="css" scoped>
  h1, h2 { text-align: center; }
  h1 { font-size: 4rem; }
  h2 { font-size: 2.5rem; }
</style>