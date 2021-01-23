<template>
  <div>
    <article
      v-for="item in content"
      :key="item.sys.id"
    >
      <h3>{{item.fields.headline}}</h3>
      <div v-html="item.fields.copy"></div>
    </article>
  </div>
</template>

<script>
import {createClient} from 'contentful'

const client = createClient({
  'space': 'xpze3evh3fd8',
  'accessToken': 'FYD0PWiJI1JCJJRicxuEzFoFh2I6EMCibmnMSeTZzo0'
})

export default {
  name: 'Contenido',
  data () {
    return {
      content: []
    }
  },
  created() {
    client.getEntries()
    .then(entries => {
      this.content = entries.items
    })
  }
}
</script>
