<template>
  <div id="app">
      <NavBar/>
      <Main/>
  </div>
</template>

<script>
import Main from './components/Main.vue'
import NavBar from './components/NavBar'
export default {
  name: 'App',
  components: {
    Main,
      NavBar
  }
}
</script>

<style>
   *{ padding: 0;
    margin: 0;
    box-sizing: border-box;
    font-family: 'Courier New', Courier, monospace;
}
body{
   background-color: lightgray;
}
</style>
