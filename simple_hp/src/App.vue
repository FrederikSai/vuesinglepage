<template>
  <div id="app">
    <front-page/>
    
  </div>
</template>

<script>
import FrontPage from './components/FrontPage'

export default {
  name: 'App',
  components: {
    FrontPage
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
  /* margin-top: 60px; */
}
.contact {
  height: 65px
}
.map {
  margin: 20px
}
</style>
