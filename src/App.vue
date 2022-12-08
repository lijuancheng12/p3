<template>
  <div id="app">
    <P3/>
  </div>
</template>

<script>
export default {
  name: 'App',
  components: {
    P3: () => import('@/views/P3.vue')
  },
}
</script>

<style lang="scss">
</style>
