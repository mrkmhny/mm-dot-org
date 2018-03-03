<template>
  <div id='app'>
    <woof/>
  </div>
</template>

<script>
import Woof from '~/components/Woof'
export default {
  name: 'Home',
  components: { Woof }
}
</script>

<style>
  @import url('https://fonts.googleapis.com/css?family=Anton');
  @import url('https://fonts.googleapis.com/css?family=Roboto');
  #app {
    background-image: url('~/static/bg.jpg');
  }
</style>
