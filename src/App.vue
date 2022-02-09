
<template>
div
  <div class="space-x-5 m-4">
    <router-link to="/" class="text-blue cursor-pointer">Home</router-link>
    <router-link to="/about" class="text-blue cursor-pointer"
      >About</router-link>
  </div>

  <router-view />
</template>

<script >

export default {
  components: {

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
  margin-top: 60px;
}
</style>
