<template>
  <div id="app">
    <Picker v-on:color-picked="filterByCampus"/>
    <transition name="fade">
      <Nav v-show="showNav" v-on:tab-picked="filterByCategory" />
    </transition>
    <transition name="fade">
      <Title v-show="showTitle" />
    </transition>
    <transition v-for="(post, i) in postsFilteredByCampusAndCategory" :key="i" name="fade">
      <Post v-if="posts.length > 0" :post="post"  v-show="showNav" />
    </transition>
  </div>
</template>

<script>
import Picker from "./components/Picker.vue";
import Nav from "./components/Nav.vue";
import Title from "./components/Title.vue";
import Post from "./components/Post.vue";
import axios from 'axios'

export default {
  name: "App",
  data() {
    return {
      // Exibition control
      showTitle: true,
      showNav: false,
      // All fetched posts
      posts: [],
      postsFilteredByCampus: [],
      postsFilteredByCampusAndCategory: []
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
    filterByCampus(campus) {
      this.showTitle = false;
      this.sleep(900).then(() => (this.showNav = true));

      // Filter posts by campus and by category === "Desenvolvimento" before selecting a tab
      this.postsFilteredByCampus = this.posts.filter((post) => post.campus === campus);
      this.postsFilteredByCampusAndCategory = this.postsFilteredByCampus.filter((post) => post.category === "Desenvolvimento");
    },
    filterByCategory(category) {
      this.postsFilteredByCampusAndCategory = this.postsFilteredByCampus.filter((post) => post.category === category);
    }
  },
  async created() {
    // Fetch all posts from mockapi
    const response = await axios.get("https://5fccd95f603c0c0016487283.mockapi.io/posts");
    this.posts = response.data;
  }
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

@screen md {

  .post-container:nth-of-type(even) {
    flex-direction: row-reverse;
  }

  .post-container:nth-of-type(even) > .image {
    @apply ml-10 mr-0;
  }

  .post-container:nth-of-type(odd) > .text > .post-title {
    @apply text-right;
  }
}

#app {
  background-color: rgb(47, 47, 47);
  @apply flex flex-col items-center justify-start min-h-screen w-full;
  min-height: calc(100vh + 1rem);
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
