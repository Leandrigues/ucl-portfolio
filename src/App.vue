<template>
  <div id="app" class="h-full">
    <Picker v-on:colorPicked="changeContent"/>
    <transition name="fade">
      <Nav v-show="showNav" />
    </transition>
    <transition name="fade">
      <Title v-show="showTitle"/>
    </transition>
  </div>
</template>

<script>
import Picker from './components/Picker.vue'
import Nav from './components/Nav.vue'
import Title from './components/Title.vue'

export default {
  name: 'App',
  data() {
    return {
      showTitle: true,
      showNav: false
    }
  },
  components: {
    Picker,
    Nav,
    Title,
  },
  methods: {
    sleep: (time) => new Promise((resolve) => setTimeout(resolve, time)),
    changeContent: function() {
      this.showTitle = false
      this.sleep(900).then(() => this.showNav = true)
    }
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
  @apply flex flex-col items-center justify-start w-full;
}

  .fade-enter-active, .fade-leave-active  {
    transition: opacity .9s;
  }

  .fade-enter, .fade-leave-to {
    opacity: 0;
  }
</style>
