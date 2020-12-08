<template>
  <div class="post-container">
    <img class="image" :src="post.image" alt="">
    <div class="text">
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
    @apply flex flex-col items-center text-white mb-10 mt-10;
    width: 90%;
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
      @apply mr-10 mt-3 w-1/2;
    }

    .text {
      @apply w-1/2;
    }

    .post-title {
      @apply text-left mt-0;
      vertical-align: top;
    }
  }
</style>
