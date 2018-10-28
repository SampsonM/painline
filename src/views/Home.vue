<template>
  <div>
    <nav :class="{'nav-open': isNavOpen, 'nav-closed': !isNavOpen}">
      <i class="fas fa-times-circle" @click="toggleNav"></i>
      <div class="menu">
        <p @click="openTime">enter times</p>
        <p @click="openLeague">lateness league</p>
      </div>
    </nav>

    <i class="fas fa-bars" @click="toggleNav" ></i>

    <!-- <lateMaybe v-show="isTimeOpen"></lateMaybe> -->
    <League v-show="isLeagueOpen"></League>
  </div>
</template>
<script>
import lateMaybe from '../components/time';
import League from '../components/league';

export default {
  name: 'Home',
  data() {
    return {
      isNavOpen: false,
      isTimeOpen: false,
      isLeagueOpen: false
    }
  },
  components: {
    lateMaybe,
    League
  },
  methods: {
    toggleNav() {
      if (window.matchMedia("(max-width: 800px)").matches) {
        this.isNavOpen = !this.isNavOpen;
      }
    },
    openTime() {
      if (window.matchMedia("(max-width: 800px)").matches) {
        this.isTimeOpen = !this.isTimeOpen;
      }

      this.toggleNav();
    },
    openLeague() {
      if (window.matchMedia("(max-width: 800px)").matches) {
        this.isLeagueOpen = !this.isLeagueOpen;
      }

      this.toggleNav();
    }
  }
}
</script>
<style lang="scss" scoped>

.tab-view {
  display: flex;
  flex-direction: row;
  width: 100%;
}

button {
  max-width: 100px;
  border-right: 1px solid #fa0;

  &:last-child {
    border-right: 0;
  }
}

nav {
  position: absolute;
  top: 0;
  right: 0;
  height: 100%;
  background: #fa0;
  
  .menu {
    margin-top: 35px;
  }

  .fa-times-circle {
    position: absolute;
    top: 10px;
    right: 10px;
    font-size: 15px;
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

.fa-bars {
  position: absolute;
  top: 15px;
  right: 15px;
}

</style>
