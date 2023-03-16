<template>
    <div class="hobbies">
        <h1>{{ msg }}</h1>
        <ul>
            <li v-for="(hobbie, idx) in hobbies" :key="idx" class="hobbies">
                {{ hobbie }} <br><br> <button v-if="isDarkMode" v-on:click="getURL(idx)" class="btn-view">View more</button>
            </li>
        </ul>
    </div>
</template>
  
<script>
export default {
    name: 'MyHobbies',
    props: {
        msg: String
    },
    data() {
        return {
            hobbies: ['Skateboarding', 'Anime', 'Genshin impact', 'Listening to music'],
            hobbiesUrl: ['https://www.youtube.com/watch?v=F1sjuey25ug', 'https://www.crunchyroll.com/es/watch/G9DUEPGJ5/asteroid-blues', 'https://genshin.hoyoverse.com/es/home', 'https://www.youtube.com/watch?v=1TW3fbGM1CU'],
            isDarkMode: true,
        }
    },
    methods: {
        getURL(idx) {
            window.open(this.hobbiesUrl[idx], '_blank');
        },
        changeButtonColor() {
            //this.isDarkMode = false
        }
    }
}
</script>
  
  <!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Kanit:wght@300&display=swap');

body {
    padding: 10px;
    font-family: 'Kanit', sans-serif;
}

h1 {
    margin: 40px 0 0;
}

ul {
    list-style-type: none;
    padding: 0;
}

li {
    display: inline-block;
    margin: 2px 10px;
    padding: 15px;
}

.btn-view {
    padding: 5px;
    border-radius: 5px;
    box-shadow: 0 8px 16px 0 rgba(0,0,0,0.2), 0 6px 20px 0 rgba(0,0,0,0.19);
    font-family: inherit;
    background-color: #A7727D;
    border: none;
    transition-duration: 0.4s;
    color: #03001C;
}

.btn-view:hover {
    background-color: #B9F3E4;
}

.hobbies {
    font-weight: bold;
}

</style>