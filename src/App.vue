<template>
  <div v-if = "isHelloWorldId">
    <img alt="Vue logo"  src="./assets/logo.png">
    <HelloWorld v-if = "isHelloWorldId" msg="Hola mundo"/>
  </div>
  <HelloWorld v-else msg= "Adios mundo"/>

  Lista de estudiantes
  <ul>
    <li v-for="(alumno, idx) in alumnos" :key="idx">
      {{ alumno }}
    </li>
  </ul>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld,
  },
  data() {
    return {
      message: "cómo estás mundo?",
      isHelloWorldId: true,
      alumnos: ['Ignacio', 'Diego', 'Raul']
    }
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
