<template>
  <div id="app" class="h-full">
    <Picker/>
  </div>
</template>

<script>
import Picker from './components/Picker.vue'

export default {
  name: 'App',
  components: {
    Picker
  }
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html, body {
  height: 100%;
}

#app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  background-color: rgb(47, 47, 47);
  @apply flex items-center justify-center w-full;
}
</style>
