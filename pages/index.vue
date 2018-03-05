<template>
  <div id='app'>
    <Cover/>
    <Content />
  </div>
</template>

<script>
import Cover from '~/components/Cover'
import Content from '~/components/Content'
export default {
  name: 'Home',
  components: { Cover, Content }
}
</script>

<style>
  @import 'normalize.css';

  html, body {
    margin: 0;
    min-height: 100vh;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: antialiased;
  }

  #app {
    min-height: 100vh;
    display: flex;
  }
</style>
