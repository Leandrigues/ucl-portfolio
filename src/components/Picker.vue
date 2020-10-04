<template>
  <div class="picker-container">
    <img :src="require('../assets/logo.svg')" alt="">
    <div class="color-picker">
      <div class="color-ball orange"></div>
      <div class="color-ball blue"></div>
      <div class="color-ball pink"></div>
      <div class="color-ball green"></div>
    </div>
  </div>
</template>

<script>
export default {

}
</script>

<style>
.picker-container {
  @apply h-full w-1/5 flex flex-col items-center
}

.color-ball {
  width: 35px;
  height: 35px;
  @apply rounded-full border border-2;
}

.color-picker {
  @apply w-full flex justify-between;
}

.pink {
  background-color: rgb(255, 38, 255);
}

.orange {
  background-color: rgb(255, 115, 0);
}

.blue {
  background-color: rgb(41, 194, 255);
}

.green {
  background-color: rgb(0, 161, 0)
}
</style>