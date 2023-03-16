<template>
  <div class="theme">
    <button class="theme-btn" id="btn-theme" v-on:click="darkMode">Dark mode</button>
  </div>
  <div v-if="isHelloWorldId">
    <img alt="Vue logo" src="./assets/spike.jpg">
    <HelloWorld v-if="isHelloWorldId" msg="Hello world" />
  </div>
  <HelloWorld v-else msg="Bye world" />
  <MyHobbies msg="These are my hobbies" v-if="isDarkMode" darkMode="dark"/>
  <MyHobbies msg="These are my hobbies" v-else darkMode="light" />
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
      this.count++;
      if (this.count % 2) {
        document.body.style.backgroundColor = '#31333D';
        document.body.style.color = '#F0F2FA';
        document.getElementById('btn-theme').innerHTML = 'Light mode';
        this.isDarkMode = true;
      } else {
        document.body.style.backgroundColor = '#ECF2FF';
        document.body.style.color = '#443C68';
        document.getElementById('btn-theme').innerHTML = 'Dark mode';
        this.isDarkMode = false;
      }
    }
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Kanit:wght@300&display=swap');

body {
  font-family: 'Kanit', sans-serif;
  color: #443C68;
  background-color: #ECF2FF;
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
  background-color: #FFF4D2;
  border: none;
  transition-duration: 0.4s;
}

img {
  height: 205px;
  margin: 15px 0;
  -webkit-transition: all 1s ease;
  -moz-transition: all 1s ease;
  -o-transition: all 1s ease;
}

img:hover {
  -webkit-transform: scale(1.3);
  -moz-transform: scale(1.3);
  -o-transform: scale(1.3);
  -ms-transform: scale(1.3);
  transform: scale(1.3)
}
</style>
