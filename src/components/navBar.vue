<template>
   <div id="nav">
      <router-link to="/">login</router-link>
      <router-link to="/Home">Home</router-link>
    </div>
</template>
<script>
export default {
  name: 'navBar'
}
</script>

<style lang="scss" scoped>
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
