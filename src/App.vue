<template>
  <div id="app">
    <nav-top></nav-top>
    <b-container>
      <router-view/>
    </b-container>
  </div>
</template>

<script>
  import NavTop from './components/elements/NavTop'
  export default {
    name: 'App',
    components: {
      NavTop
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
}
</style>
