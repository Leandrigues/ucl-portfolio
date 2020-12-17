<template>
  <div class="nav-container">
    <button v-for="(tab, i) in tabs" :key="i" class="tab" @click="$emit('tab-picked', tab)">{{ tab }}</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      tabs: ["Desenvolvimento", "Pesquisa", "Aulas", "Eventos", "Contatos"]
    }
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Commissioner:wght@600&display=swap');

.tab:focus {
  outline: none;
  border: none;
  @apply font-bold;
}

.nav-container {
  @apply flex flex-wrap justify-around w-full mt-16 justify-around;
}

.tab {
  @apply text-white text-base px-4 mb-4;
  font-family: 'Commissioner', sans-serif;
}

@screen md {
  .nav-container {
    @apply w-1/3;
  }
}
</style>