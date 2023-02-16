//Posts.vue

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
      <h1 class="title">
        Hiii
      </h1>
      <Sidebar>
        <ul class="sidebar-panel-nav">
          <li><a href="/">Home</a></li>
          <li><a href="#about">About</a></li>
          <li><a href="#contact">Contact</a></li>
        </ul>
      </Sidebar>
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

.imgfun {
  width: 20%;
}

.vel-img-title {
  font-size: 144 px;
  padding: 5em;
  color: rgb(31, 16, 16);
  font-family: "courier";
  background-color: #000000;
  display: inline-block;
  vertical-align: middle;
  transform: translateZ(0);
  box-shadow: 0 0 1px rgba(0, 0, 0, 0);
  backface-visibility: hidden;
  -moz-osx-font-smoothing: grayscale;
  transition-duration: 0.3s;
  transition-property: transform;
}

.vel-img-title:hover {
  transform: scale(2.1);
}

.container2 {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  text-align: center;
}
.logo {
  align-self: center;
  color: rgb(248, 7, 7);
  font-weight: bold;
  font-family: "Lato";
}

.main-nav {
  display: flex;
  justify-content: space-between;
  padding: 0.5rem 0.8rem;
}
.sidebar-panel-nav {
  list-style-type: none;
}
.sidebar-panel-nav li a {
  color: rgb(19, 180, 14);
  text-decoration: none;

  font-size: 1.5rem;
  display: block;
  padding-bottom: 0.5em;
  color: rgb(24, 7, 7);
  font-weight: bold;
  font-family: "Lato";
}

.title {
  font-family: "Quicksand", "Source Sans Pro", -apple-system, BlinkMacSystemFont,
    "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #26643b;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}

.gallery {
  display: flex;
  flex-direction: column;
  margin: 0 auto;
}

.pic {
  cursor: pointer;
  max-width: 700px;

  margin: 35px auto;
  padding: 20px;
}

.pic img {
  width: 100%;
  padding-top: 10px;
}
</style>

<nuxt-link
  :key="page.path"
  :to="page.path === '/info/index' ? '/info' : page.path"
  class="menu-link"
>
                    {{ page.title }}
                </nuxt-link>
