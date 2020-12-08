<template>
  <div id="app">
    <Picker v-on:colorPicked="changeContent" />
    <transition name="fade">
      <Nav v-show="showNav" />
    </transition>
    <transition name="fade">
      <Title v-show="showTitle" />
    </transition>
    <transition v-for="(post, i) in filteredByCampusAndCategory(selectedCampus, selectedCategory)" :key="i" name="fade">
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
      showTitle: true,
      showNav: false,
      selectedCampus: "butanta",
      selectedCategory: "dev",
      posts: [],
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

    filteredByCampusAndCategory(campus, category) {
      const filtered = this.posts.filter((post) => {
        return post.campus === campus && post.category === category
      })
      return filtered
    }
  },
  async created() {
    const response = await axios.get("https://5fccd95f603c0c0016487283.mockapi.io/posts")
    this.posts = response.data
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
  /* min-height: calc(100%);  */
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
