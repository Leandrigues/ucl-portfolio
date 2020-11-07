<template>
  <div id="app" class="h-full">
    <Picker v-on:colorPicked="changeContent" />
    <transition name="fade">
      <Nav v-show="showNav" />
    </transition>
    <transition name="fade">
      <Title v-show="showTitle" />
    </transition>
    <transition v-for="(post, i) in posts" :key="i" name="fade">
      <Post :post="post"  v-show="showNav" />
    </transition>
  </div>
</template>

<script>
import Picker from "./components/Picker.vue";
import Nav from "./components/Nav.vue";
import Title from "./components/Title.vue";
import Post from "./components/Post.vue";

export default {
  name: "App",
  data() {
    return {
      showTitle: true,
      showNav: false,
      posts: [
        {
          title: "dev.boost",
          description:
            "Lorem, ipsum dolor sit amet consectetur adipisicing elit. Dolore minima voluptate suscipit fuga laboriosam laudantium, ad commodi dicta soluta recusandae labore ipsam architecto, repellat sapiente voluptatum sunt aliquam quod nemo dolor atque, ea dolorum illum! Iusto, temporibus earum. Dolorum, similique hic nisi reiciendis distinctio, perferendis provident odio veritatis quas, reprehenderit temporibus adipisci.",
          image: 'image'
        },
        {
          title: "dev.boost",
          description:
            "Lorem, ipsum dolor sit amet consectetur adipisicing elit. Dolore minima voluptate suscipit fuga laboriosam laudantium, ad commodi dicta soluta recusandae labore ipsam architecto, repellat sapiente voluptatum sunt aliquam quod nemo dolor atque, ea dolorum illum! Iusto, temporibus earum. Dolorum, similique hic nisi reiciendis distinctio, perferendis provident odio veritatis quas, reprehenderit temporibus adipisci.",
          image: 'image'
        },
      ],
    };
  },
  components: {
    Picker,
    Nav,
    Title,
    Post,
  },
  methods: {
    sleep: (time) => new Promise((resolve) => setTimeout(resolve, time)),
    changeContent: function() {
      this.showTitle = false;
      this.sleep(900).then(() => (this.showNav = true));
    },
  },
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.post-container:nth-of-type(2n) {
  flex-direction: row-reverse;
}

.post-container:nth-of-type(2n) > .image {
  @apply ml-10 mr-0;
}
#app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
    @apply min-h-screen;
  background-color: rgb(47, 47, 47);
  @apply flex flex-col items-center justify-start  w-full;
}

.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.9s;
}

.fade-enter,
.fade-leave-to {
  opacity: 0;
}
</style>
