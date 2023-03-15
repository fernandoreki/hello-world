<template>
  <div class="theme">
    <button class="theme-btn" id="btn-theme" v-on:click="darkMode">Dark mode</button>
  </div>
  <div v-if="isHelloWorldId">
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld v-if="isHelloWorldId" msg="Hello world" />
  </div>
  <HelloWorld v-else msg="Bye world" />
  <MyHobbies msg="These are my hobbies 😎" />
</template>

<script>
import HelloWorld from './components/HelloWorld.vue';
import MyHobbies from './components/MyHobbies.vue';

/* tarea */

export default {
  name: 'App',
  components: {
    HelloWorld,
    MyHobbies,
  },
  data() {
    return {
      message: "cómo estás mundo?",
      isHelloWorldId: true,
      alumnos: ['Ignacio', 'Diego', 'Raul'],
      isDarkMode: false,
      count: 0,
    }
  },
  methods: {
    letterCounter(name) {
      return name.length;
    },
    darkMode() {
      this.count ++;
      if (this.count % 2) {
        document.body.style.backgroundColor = '#31333D';
        document.body.style.color = '#F0F2FA';
        document.getElementById('btn-theme').innerHTML = 'Light mode';
      } else {
        document.body.style.backgroundColor = 'white';
        document.body.style.color = '#25629e';
        document.getElementById('btn-theme').innerHTML = 'Dark mode';
      }
    }
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Kanit:wght@300&display=swap');

body {
  font-family: 'Kanit', sans-serif;
  color: #25629e;
}

#app {
  font-family: Verdana, Geneva, Tahoma, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  margin-top: 60px;
}

.theme {
  text-align: right;
  padding-right: 5%;
  padding-top: 2%;
}

#btn-theme {
    padding: 5px;
    border-radius: 5px;
    font-family: inherit;
}
</style>
