<template>
  <div id="app">
    <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
    <HelloWorld msg="Welcome to Your Vue.js App"/>
    <vue-scroll-progress-bar @complete="handleComplete" height="1rem" />
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import Vue from 'vue'
import VueScrollProgressBar from '@guillaumebriday/vue-scroll-progress-bar'
 
Vue.use(VueScrollProgressBar)

export default {
  name: 'App',
  components: {
    HelloWorld
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  width: 100vw;
  /* height: 500vh; */
}
html, body {
    margin: 0;
    padding: 0;
    width: 100%;
    height: 100vh;
    font-family: Helvetica;
    scroll-behavior: smooth;
}

</style>
