<template>
  <div class="nav-bar">
    <ul>
      <li>
        <NuxtLink to="/">Home</NuxtLink>
      </li>
      <li>
        <NuxtLink to="/trending">Trending Page</NuxtLink>
      </li>
    </ul>
  </div>
</template>

<style lang="scss" scoped>
ul {
  list-style: none;
  margin: 0;
  padding: 0;
}
li {
  display: inline-block;
  margin-right: 1rem;
}
</style>
