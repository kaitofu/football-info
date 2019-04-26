<template lang="pug">
#app
  img(alt='Vue logo', src='./assets/logo.png')
  HelloWorld(msg='Welcome to Your Vue.js App')
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

const axios = require('axios');

export default {
  name: 'app',
  components: {
    HelloWorld
  },
  mounted() {
    axios({
      headers: { 'X-Auth-Token': 'b23df29ea8e94c24a284785921d5c666' },
      url: 'https://api.football-data.org/v2/matches',
      method: 'get'
    })
    .then(function (response) {
      console.log(response);
    })
    .catch(function (error) {
      console.log(error);
    })
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
