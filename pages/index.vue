<template>
  <div class="container">
    <nav class="main-nav">
      <div class="logo">Art is Everywhere</div>
    </nav>

    <div class="container2">
      <div class="gallery">
        <div
          v-for="(img, idx) in imgs"
          :key="idx"
          class="pic"
          @click="() => show(idx)"
        >
          <img :src="img.src ? img.src : img" />
        </div>

        <h1 class="title">Hiii</h1>
        <Logo />
        <div class="links">
          <a
            href="./blog"
            target="_blank"
            rel="noopener noreferrer"
            class="button--green"
          >
            My Posts
          </a>
          <a
            href="https://github.com/nuxt/nuxt.js"
            target="_blank"
            rel="noopener noreferrer"
            class="button--grey"
          >
            GitHub
          </a>
        </div>
        <client-only>
          <vue-easy-lightbox
            :visible="visible"
            :index="index"
            :imgs="imgs"
            @hide="visible = false"
            @on-prev="handlePrev"
            @on-next="handleNext"
          />
        </client-only>
      </div>
    </div>
  </div>
</template>

<script>
import Sidebar from "../components/Sidebar.vue";

// Importing images to generate URL is a feature of webpack's loader.
// Here is the usage in <script /> , which is the same as in `.js`.

// way1:
import DancingImgUrl from "../assets/dancing1.jpg";
import Unity from "../assets/unity.jpg";
import Progress from "../assets/progress.jpg";

import Judee from "../assets/judee.jpg";
import GratefulUrl from "../assets/grateful1.jpg";

import PostMasc1 from "../assets/postmasc1.jpg";

import Inherent from "../assets/inherent.jpg";

// way2:
// const GratefulUrl = require("~/assets/grateful1.jpg");
// const PostMasc1 = require("~/assets/postmasc1.jpg");

// const Inherent = require("~/assets/inherent.jpg");

// Compare the log results with the local path.
console.log(DancingImgUrl);
console.log(GratefulUrl);

export default {
  name: "index",
  components: {
    Sidebar,
  }
  // ,
//   data() {
//     return {
//       imgs: [
//         {
//           src: DancingImgUrl,
//           title: "Artist: Adam Aslan Title: 'Dancing' ",
//           description: "this is an XY graph.",
//         },
//         {
//           GratefulUrl,
//         },
//         {
//           src: PostMasc1,
//           title: "The postmasculine identity",
//           description: "this is an XY graph.",
//         },
//         { src: Inherent, title: "What makes Order Inherent?" },
//         { src: Judee, title: "Judee Sill" },
//         { src: Unity, title: "Unity and Individuality" },
//         { src: Progress, title: "Definition of Progress" },
//       ],
//       visible: false,
//       index: 0, // default
//     };
//   },
//   methods: {
//     show(index) {
//       this.index = index;
//       this.visible = true;
//     },
//     handlePrev(oldIndex, newIndex) {
//       console.log("when next btn click ----");
//       console.log("oldIndex of imgs:", oldIndex);
//       console.log("newIndex of imgs:", newIndex);
//     },
//     handleNext(oldIndex, newIndex) {
//       console.log("when next btn click ----");
//       console.log("oldIndex of imgs:", oldIndex);
//       console.log("newIndex of imgs: ", newIndex);
//     },
//   },
// };
</script>
//list-styletype -> .sidebar-panel-nav li a
<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
}
.burger {
  align-content: right;
  justify-content: right;
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
