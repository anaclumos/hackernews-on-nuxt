<template>
  <div>
    <h1>HackerNews on Nuxt</h1>
    <div v-if="pending">Loading ...</div>
    <div v-else>
      <ul>
        <li v-for="item in items">
          <NuxtLink :to="item.url">{{ item.title }}</NuxtLink>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      items: [],
      pending: true,
    }
  },
  async created() {
    const response = await fetch('https://hacker-news.firebaseio.com/v0/topstories.json')
    const ids = await response.json()
    const promises = ids.slice(0, 10).map((id) => fetch(`https://hacker-news.firebaseio.com/v0/item/${id}.json`))
    const responses = await Promise.all(promises)
    const result = await Promise.all(responses.map((r) => r.json()))
    console.log(result)
    this.items = result
    this.pending = false
  },
}
</script>
