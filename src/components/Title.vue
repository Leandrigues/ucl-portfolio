<template>
  <div class="title">
    USPCodeLab
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
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Josefin+Slab:wght@300&family=Poiret+One&family=Rajdhani:wght@300&family=Raleway:wght@450&display=swap');

.title {
  /* font-family: 'Rajdhani', sans-serif; */
  /* font-family: 'Poiret One', cursive; */
  /* font-family: 'Josefin Slab', serif; */
  font-family: 'Raleway', sans-serif;
  transition: 1s display;
  @apply text-xl text-white mt-10;
}

@screen md {
  .title {
    @apply text-5xl
  }
}
</style>
