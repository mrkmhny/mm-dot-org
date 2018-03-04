<template>
  <div id='app'>
    <cover/>
  </div>
</template>

<script>
import Cover from '~/components/Cover'
export default {
  name: 'Home',
  components: { Cover }
}
</script>

<style>
  @import 'normalize.css';
  @import url('https://fonts.googleapis.com/css?family=Anton');
  @import url('https://fonts.googleapis.com/css?family=Raleway');
  @import url('https://fonts.googleapis.com/css?family=Roboto');

  html, body {
    margin: 0;
    min-height: 100vh;
  }

  #app {
    min-height: 100vh;
    background: linear-gradient(140deg,rgba(68, 68, 68, 0.6) 20%, rgba(0, 0, 0, 0.2)), url('~/static/bg.jpg') #666666;
  }
</style>
