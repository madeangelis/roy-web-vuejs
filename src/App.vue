<template>
  <Navbar />
  <Footer />
  <div id="nav">
    <router-link to="/">Home</router-link> |
    <router-link to="/about">About</router-link> |
    <router-link to="/retro">Retro</router-link>
  </div>
  <router-view />
</template>

<script>
import Navbar from "./components/Navbar.vue";
import Footer from "./components/Footer.vue";

export default {
  name: "App",
  components: {
    Navbar,
    Footer,
  },
};
</script>

<style>
body {
  font-family: "Open Sans", sans-serif;
}

body::-webkit-scrollbar {
  width: 8px;
  height: 8px;
  background-color: rgba(0, 0, 0, 0.9);
}
/* Add a thumb */
body::-webkit-scrollbar-thumb {
  background: rgba(250, 250, 250, 0.5);
}

body,
html {
  height: 100%;
  min-height: 100%;
  overflow-x: hidden;
}
</style>
