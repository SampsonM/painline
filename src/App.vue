<template>
  <div id="app">
    <div id="nav">
      <router-link to="/">login</router-link>
      <router-link to="/Home">Home</router-link>
    </div>
    <router-view />
  </div>
</template>

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
#nav {
  padding: 20px;
  width: 100%;
  background: #fa0;
}

#nav a {
    padding: 15px;
    font-weight: bold;
    color: #2c3e50;
    border: 1px solid #f0f0f0;
    border-top: 0;
    border-bottom: 0;

    &:last-child {
      border-left: 0;
    }
}

#nav a.router-link-exact-active {
  color: #fff;
}
</style>
