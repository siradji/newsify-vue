<template>
  <div id="app">
    <Header />
  </div>
</template>

<script>
import Header from './components/layout/Header.vue';
export default {
  name: 'App',
  components: {
    Header
  }
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin: 0 auto;
  max-width: 80%;
}
body {
  background: #000;
  color: #fff;
}


</style>
