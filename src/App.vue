<template>
  <div id="app">
    <router-view/>
  </div>
</template>

<script>
export default {
}
</script>

<style lang="scss">
@import "assets/scss/main.scss";

@media screen and (max-width: 500px) {
#app {
  max-width: 400px;
}
    
}
</style>
