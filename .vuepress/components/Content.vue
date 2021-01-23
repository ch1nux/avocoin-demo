<template>
  <article>
    <h2>{{ title }}</h2>
    <div v-html="text"></div>
  </article>
</template>

<script>
export default {
  name: 'Content',
  props: {
    title: String,
    text: String
  }
}
</script>

<style lang="css" scoped>
article { margin: 1rem; }
</style>