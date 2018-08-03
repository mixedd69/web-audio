<template>
  <div id="app">
    <div class="bg"></div>
    <MusicPlayer></MusicPlayer>
  </div>
</template>

<script>
import MusicPlayer from "./components/MusicPlayer.vue";

export default {
  name: "app",
  components: {
    MusicPlayer
  }
};
</script>

<style lang="scss">
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
body,
html {
  overflow: hidden;
}
.bg {
  background: linear-gradient(rgba(0, 0, 0, 0.45), rgba(0, 0, 0, 0.45)),
    url("https://www.rockandpop.cl/wp-content/uploads/2017/03/Incubus.jpg")
      no-repeat center center fixed;
  position: absolute;
  height: 100%;
  width: 100%;
  filter: blur(3px);
  background-size: cover;
  transform: scale(1.02);
}
</style>
