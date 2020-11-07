<template>
  <div class="post-container">
    <img class="image" src="https://miro.medium.com/max/10368/1*eyhPjT5BII1juyvr715XIQ.jpeg" alt="">
    <div>
      <div class="post-title">{{ post.title }}</div>
      <div class="post-description">{{ post.description }}</div>
    </div>
  </div>
</template>

<script>
export default {
  props: ['post'],
  data() {
    return {
    };
  },
};
</script>

<style scoped>
  .post-container {
    @apply flex flex-col items-center text-white;
    width: 80%;
  }

  .post-title {
    @apply text-3xl text-center mt-4 mb-4 font-bold;
  }

  .post-description {
    @apply text-center;
    text-align: justify;
    text-justify: inter-word
  }

  @screen md {
    .post-container {
      @apply flex-row justify-start items-start mt-10 w-1/2;
    }

    .image {
      width: 400px;
      @apply mr-10 mt-3;
    }

    .post-title {
      @apply text-left mt-0;
      vertical-align: top;
    }
  }
</style>
