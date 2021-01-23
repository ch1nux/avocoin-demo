<template>
  <div>
    <h1>Avocoin</h1>
    <h2>1 BTC &rarr; {{ price }}🥑</h2>
  </div>
</template>

<script>
export default {
  name: 'PriceAvocado',
  data () {
    return {
      price: 0
    }
  },
  created() {
    fetch('https://avocoinapp.herokuapp.com/')
    .then(response => response.json())
    .then(data => {
      this.price = data.price
    })
  }
}
</script>

<style lang="css" scoped>
  h1, h2 { text-align: center; }
  h1 { font-size: 4rem; }
  h2 { font-size: 2.5rem; }
</style>