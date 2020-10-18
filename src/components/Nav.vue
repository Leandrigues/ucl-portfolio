<template>
  <div class="nav-container">
    <button class="tab">Timeline</button>
    <button class="tab">Hoje</button>
    <button class="tab">Contato</button>
  </div>
</template>

<script>
export default {

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
  @apply flex justify-around w-1/5 mt-16;
}

.tab {
  @apply text-white text-lg;
  font-family: 'Commissioner', sans-serif;
}
</style>