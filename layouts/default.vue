<template>
  <main>
    <NavBar />
    <slot />
  </main>
</template>

<style lang="scss">
main {
  padding: 1rem;
}
body {
  background: #fafafa;
  margin: 0 auto;
  font-family: ui-sans-serif, -apple-system, BlinkMacSystemFont, 'Apple SD Gothic Neo', Pretendard, system-ui,
    -system-ui, sans-serif, 'Apple Color Emoji';
  max-width: 50rem;
}
</style>
