<template>
  <h1>Make your own cake!</h1>

  <Caker />
</template>

<script>
import Caker from "./components/Caker.vue";

export default {
  name: "App",
  components: {
    Caker,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
