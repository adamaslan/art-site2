<template>
  <div class="container">
    <nav class="main-nav">
      <div class="logo">
        Blog Pain
      </div>
      <Burger></Burger>
    </nav>

    <div>
      <Logo />

      <Sidebar>
        <ul class="sidebar-panel-nav">
          <li><a href="/">Home</a></li>
          <li><a href="#about">About</a></li>
          <li><a href="#contact">Contact</a></li>
        </ul>
      </Sidebar>
    </div>
    <nuxt-child v-if="page" />
    <div>
      <h1>Blog Posts</h1>
      <ul>
        <li v-for="article of articles" :key="article.slug">
          <NuxtLink :to="{ name: 'blog-slug', params: { slug: article.slug } }">
            <img :src="article.img" />
            <div>
              <h2>{{ article.title }}</h2>
              <p>by {{ article.author.name }}</p>
              <p>{{ article.description }}</p>
            </div>
          </NuxtLink>
        </li>
      </ul>
    </div>
  </div>
</template>
<script>
import Burger from "../components/Burger.vue";
import Sidebar from "../components/Sidebar.vue";

export default {
  name: "index",
  components: {
    Burger,
    Sidebar
  },

  async asyncData({ $content, params }) {
    const articles = await $content("articles")
      .only(["title", "description", "img", "slug", "author"])
      .sortBy("createdAt", "asc")
      .fetch();

    return {
      articles
    };
  }
};
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
}

.burger {
  align-content: right;
  justify-content: right;
}
</style>
