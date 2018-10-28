<template>
  <div>
    <Menu :isNavOpen="isNavOpen" @close-menu="toggleNav"
    @open-time="toggleLate"
    @open-league="toggleLeague"></Menu>

    <i class="fas fa-bars" @click="toggleNav" ></i>

    <lateMaybe v-show="isLateOpen" @open-late="toggleLate"></lateMaybe>
    <League v-show="isLeagueOpen" @open-league="toggleLeague"></League>
  </div>
</template>
<script>
import lateMaybe from '../components/lateMaybe';
import League from '../components/league';
import Menu from '../components/menu.vue';

export default {
  name: 'Home',
  data() {
    return {
      isNavOpen: false,
      isLateOpen: false,
      isLeagueOpen: false
    }
  },
  components: {
    lateMaybe,
    League,
    Menu
  },
  methods: {
    toggleNav() {
      this.isNavOpen = !this.isNavOpen;
    },
    toggleLate() {
      this.isLateOpen = !this.isLateOpen;
      this.toggleNav();
    },
    toggleLeague() {
      this.isLeagueOpen = !this.isLeagueOpen;
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



.fa-bars {
  position: absolute;
  top: 15px;
  right: 15px;
  font-size: 30px;
}

</style>
