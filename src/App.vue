<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <HelloWorld msg="Hola mundo"/>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld
  }
}
</script>

<style>
body {
  background-color: rgb(234, 189, 248);
}

#app {
  font-family: Verdana, Geneva, Tahoma, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #1b4d7e;
  margin-top: 60px;
  background-color: bisque;
}
</style>
