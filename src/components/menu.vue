<template>
  <nav :class="{'nav-open': isNavOpen, 'nav-closed': !isNavOpen}">
      <i class="fas fa-times-circle" @click="closeMenu"></i>
      <div class="menu">
        <p @click="openTime">enter times</p>
        <p @click="openLeague">lateness league</p>
      </div>
    </nav>
</template>
<script>
export default {
  props: ['isNavOpen'],
  methods: {
    closeMenu() {
      this.$emit('close-menu')
    },
    openTime() {
      this.$emit('open-time')
    },
    openLeague() {
      this.$emit('open-league')
    }
  }
}
</script>
<style lang="scss" scoped>
nav {
  position: absolute;
  top: 0;
  right: 0;
  height: 100%;
  background: #fa0;
  z-index: 1;
  
  .menu {
    margin-top: 60px;
  }

  .fa-times-circle {
    position: absolute;
    top: 15px;
    right: 15px;
    font-size: 30px;
  }

  p {
    border-top: 2px solid #fafafa;
    border-bottom: 2px solid #fafafa;
    margin: auto;
    padding: 5px;

    &:last-child {
      border-top: 0;
    }
  }
}

.nav-open {
  width: 100%;
  display: block;
}

.nav-closed {
  width: 0;
  display: none;
}
</style>
