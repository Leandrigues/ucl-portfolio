<template>
  <div class="picker-container">
    <Logo :logoMainColor="logoMainColor" :logoSecondaryColor="logoSecondaryColor" :logoTertiaryColor="logoTertiaryColor"/>
    <div class="color-picker">
      <button @click="setLogoColor('#ff7825', '#ffa46d', '#ff8b46')" class="color-ball orange"></button>
      <button @click="setLogoColor('#5ec8ae', '#99daca', '#75d0ba')" class="color-ball blue"></button>
      <button @click="setLogoColor('#e23caa', '#ea7bc5', '#e559B8')" class="color-ball pink"></button>
      <button @click="setLogoColor('green', '#5bbd5b', 'green')" class="color-ball green"></button>
    </div>
  </div>
</template>

<script>
import Logo from './Logo'

export default {
  components: {
    Logo
  },
  data() {
    return {
      logoMainColor: '#ffffff',
      logoSecondaryColor: '#c8c8c8',
      logoTertiaryColor: '#d4d4d4',
    }
  },
  methods: {
    setLogoColor: function(main, secondary, tertiary) {
      this.logoMainColor = main
      this.logoSecondaryColor = secondary
      this.logoTertiaryColor = tertiary
      this.$emit('colorPicked')
    }
  }
}
</script>

<style>
.picker-container {
  @apply w-56 flex flex-col items-center
}

.color-ball:focus {
  outline: none;
  @apply border border-2;
}

path {
  transition: 0.5s fill;
}

.color-ball {
  width: 35px;
  height: 35px;
  @apply rounded-full;
}

.color-picker {
  @apply w-full flex justify-between;
}

.pink {
  background-color: rgb(253, 57, 253);
}

.orange {
  background-color: #ff7825;
}

.blue {
  background-color: #04dab3;
}

.green {
  background-color: rgb(3, 148, 3)
}
</style>