<template>
  <div class="post-container">
    <img class="image" src="https://miro.medium.com/max/10368/1*eyhPjT5BII1juyvr715XIQ.jpeg" alt="">
    <div class="text">
      <div class="post-title">{{ posts[0].title }}</div>
      <div class="post-description">{{ posts[0].description }}</div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      posts: [
        {
          title: "dev.boost",
          description:
            "Lorem, ipsum dolor sit amet consectetur adipisicing elit. Dolore minima voluptate suscipit fuga laboriosam laudantium, ad commodi dicta soluta recusandae labore ipsam architecto, repellat sapiente voluptatum sunt aliquam quod nemo dolor atque, ea dolorum illum! Iusto, temporibus earum. Dolorum, similique hic nisi reiciendis distinctio, perferendis provident odio veritatis quas, reprehenderit temporibus adipisci. Eligendi illo iste voluptatibus totam facere autem dolorem rem, officiis ea? Quae esse nesciunt id laudantium, natus dignissimos rem eius. Earum voluptates sint pariatur perferendis esse illo. Reiciendis optio molestias maiores obcaecati eius laborum eaque magnam perferendis reprehenderit consequatur provident veritatis, facilis necessitatibus fuga ducimus vitae corporis ea!",
          image: 'image'
        },
      ],
    };
  },
};
</script>

<style scoped>
  .post-container {
    @apply flex flex-col pt-10 items-center text-white;
    width: 80%;
  }

  .post-title {
    @apply text-3xl text-center mt-4 mb-4 font-bold;
  }

  .post-description {
    letter-spacing: 1.1px;
    @apply text-center;
    text-align: justify;
    text-justify: inter-word
  }

  .image {
    width: 100%;
    height: 300px;
  }

  @screen md {
    .post-container {
      @apply flex-row justify-start items-start w-1/2;
    }

    .image {
      width: 400px;
      height: 400px;
      @apply mr-10 mt-3;
    }

    .post-title {
      @apply text-left mt-0;
      vertical-align: top;
    } 
  }
</style>
