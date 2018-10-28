<template>
  <div id="app">
    <Nav-Bar></Nav-Bar>
    <router-view />
  </div>
</template>
<script>
import NavBar from './components/navBar'

export default {
  components: {
    NavBar
  }
}
</script>

<style lang="scss" scoped>
* {
  box-sizing: border-box;
}

#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  padding: 0;
  margin: 0;
  height: 100vh;
  width: 100%;
}

</style>
