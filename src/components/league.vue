<template>
  <div class="league">
    <button @click="toggleBoard"></button>
    <button @click="toggleBoard"></button>

    <div v-show="board" class="people">
      <LeegTable :mock="mock.people"></LeegTable>
    </div>

    <div v-show="!board" class="rail">
      <LeegTable :mock="mock.trains"></LeegTable>
    </div>

  </div>
</template>
<script>
import mock from '../assets/mock.json';
import LeegTable from './table';

export default {
  name: 'league',
  data() {
    return {
      board: true,
      mock
    }
  },
  components: {
    LeegTable
  },
  methods: {
    toggleBoard() {
      board = !board;
    }
  }
}
</script>
<style lang="scss" scoped>
.league {
  position: absolute;
  top: 0;
  left: 0;
  height: 100%;
  width: 100vw;
  background: green;
}

button {
  color: red;
  background: blue;
}
</style>
