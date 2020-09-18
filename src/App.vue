<template>
  <div id="app">
    <app-index></app-index>
  </div>
</template>

<script>

export default {
  name: 'App',
  components: {
    'appIndex' : () => import('@/Views/index')
  }
}
</script>

<style lang="scss">
#app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
</style>
