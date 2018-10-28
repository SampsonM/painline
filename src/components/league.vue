<template>
  <div class="league">
    <div class="buttons"> 
      <button @click="toggleBoard">People</button>
      <button @click="toggleBoard">Rail</button>
    </div>

    <div v-show="board" class="people">
      <Chart label="people" :mock="mock.people"></Chart>
    </div>

    <div v-show="!board" class="rail">
      <Chart label="trains" :mock="mock.trains"></Chart>
    </div>

  </div>
</template>
<script>
import mock from '../assets/mock.json';
import LeegTable from './table';
import Chart from './chart';

export default {
  name: 'league',
  data() {
    return {
      board: false,
      mock
    }
  },
  components: {
    LeegTable,
    Chart
  },
  methods: {
    toggleBoard() {
      this.board = !this.board;
    }
  }
}
</script>
<style lang="scss" scoped>
.buttons {
  display: flex;
  flex-direction: row;
  width: 600px;
}
.league {
  position: absolute;
  top: 0;
  left: 0;
  height: 100%;
  width: 100vw;
  background: rgb(56, 56, 56);
}

button {
  color: red;
  background: blue;
  width: 50px;
  height: 20px;
}

.people {
  width: 100%;
  height: 400px;
}
.rail {
  width: 100%;
  height: 400px;
}
</style>
